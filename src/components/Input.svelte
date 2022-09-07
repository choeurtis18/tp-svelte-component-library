<script>

    export let type = ''; 
    export let texte = '';
    export let placeholder ='';
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
        <input type="password" id="pass" name="password" placeholder={placeholder ? placeholder : "Enter your Password"} bind:value={ value }
            minlength="8" required>
        {#if value.length < 7 && value.length > 0}
            <span class="error">This field is short</span>
        {/if}
    </div>
{:else if type === 'email'}
    <div class="input-field">
        <label for="email">{texte ? texte : "Email"}</label>
        <input type="email" id="email" name="email" placeholder={placeholder ? placeholder : "Enter your Email"} bind:value={ value } required>
        {#if !value.includes("@") && value.length > 0}
            <span class="error">This email is invalid</span>
        {/if}
    </div>
{:else if type === 'regural'}
    <div class="input-field">
        <label for="field">{texte ? texte : "Field"}</label>
        <input type="text" id="field" name="field" placeholder={placeholder ? placeholder : "Enter your name"} required>
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
        max-width: 350px;
        margin: 0 auto 20px auto;
    }
    .error {
        color: #6083A9;
        margin-top: 5px;
        font-size: 0.8em;
        text-align: right;
    }
    label {
        color: #394756;
        font-size: 1em;
        margin-bottom: 5px;
        font-weight: 600;
    }
    input, textarea {
        border: 1px solid #3947566b;
        border-radius: 3px;
        outline: none;
        padding: 8px 10px ;
    }
    input:focus, textarea:focus {
        outline: 1px solid #394576c4;
    }
    input::placeholder {
        color: #949494;
        font-size: 0.95em;
    }
</style>