<script>

    export let type = ''; 
    export let texte = '';
    let value = "";

    
    const showInput = () => {
        if(document.querySelector('#pass').type == 'password') {
            document.querySelector('#pass').type = 'text';
            document.querySelector('#pass').closest('.input-field')
                .querySelector('i').classList.add('fa-eye-slash');
        } else {
            document.querySelector('#pass').type = 'password';
            document.querySelector('#pass').closest('.input-field')
                .querySelector('i').classList.remove('fa-eye-slash');
        }
    };
</script>

{#if type === 'password'}
    <div class="input-field">
        <label for="pass">
            {texte ? texte : "Password"}
            <i class="fa fa-eye" style="cursor:pointer" on:click={ showInput }></i>
        </label>
        <input type="password" id="pass" name="password" bind:value={ value }
            minlength="8" required>
        {#if value.length < 7 && value.length > 0}
            <span class="error">This field is short</span>
        {/if}
    </div>
{:else if type === 'email'}
    <div class="input-field">
        <label for="email">{texte ? texte : "Email"}</label>
        <input type="email" id="email" name="email" bind:value={ value } required>
        {#if !value.includes("@") && value.length > 0}
            <span class="error">This email is invalid</span>
        {/if}
    </div>
{:else if type === 'regural'}
    <div class="input-field">
        <label for="field">{texte ? texte : "Field"}</label>
        <input type="text" id="field" name="field" required>
    </div>
{:else if type === 'textarea'}
    <div class="input-field">
        <label for="textarea">{texte ? texte : "textarea"}</label>
        <textarea type="text" maxlength="200" id="textarea" name="textarea" 
            style="height: 128px;" required>
        </textarea>
    </div>
{/if}

<style>
    .input-field {
        display: flex;
        flex-direction: column;
        text-align: left;
    }
    .error {
        color: #f14668;
    }
</style>