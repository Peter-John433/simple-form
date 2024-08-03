<template>
    <div>
        <form 
            @submit.prevent="handleSubmit"
            :class="{ isForm: formClass}"
        >
            <label>
                name
                <input type="text" v-model="name" required>
            </label>
            <label>
                email
                <input type="email" v-model="email" required>
            </label>
            <label>
                password
                <input type="password" v-model="password" required>
                <p class="pass">{{ passwordP }}</p>
            </label>
            <label>
                role
                <select required v-model="role">
                    <option value="choose" disabled>choose a skill</option>
                    <option value="front">frontend developer</option>
                    <option value="back">backend developer</option>
                    <option value="designer">ui/ux designer</option>
                </select>
            </label>
            <div class="check">
                <input type="checkbox" v-model="checkMe" required>
                accept sipa-K terms and conditions ?
            </div>
            <div class="btn">
                <button>submit</button>
            </div>
            <div>
                {{ nameP }}
            </div>
        </form>
    </div>
</template>
<script>
 export default{
    name: 'section-two',
    data(){
        return{
            formClass: true,
            name: '',
            email: '',
            password: '',
            role: 'choose',
            checkMe: false,
            emailP: '',
            passwordP: '',
            nameP: ''
        }
    },
   
    methods:{
        handleSubmit(){
            if(this.password.length < 5 ){
                this.$swal.fire({
                    title: 'Error!',
                    text: this.passwordP = 'password must be atleast 5',
                    icon: 'error',
                    confirmButtonText: 'rewrite password',
                    confirmButtonColor: 'red'
                })
                this.passwordP = 'invalid password'
            }else{
                this.$swal.fire({
                    title: 'Application successful',
                    text: this.passwordP = 'form submitted successful',
                    icon: 'success',
                    confirmButtonText: 'confirmed',
                    confirmButtonColor: 'green'
                })

                this.passwordP = 'valid password'
            }

            this.name = ''
            this.email = ''
            this.password = ''
            this.role = 'choose'
            this.checkMe = false
        }
    }
 }
</script>
<style scoped>
    label{
        /* background-color: red; */
        width: 100%;
        display: block;
        text-transform: capitalize;
        font-size: 12px;
    }

    input{
        width: 100%;
        padding: 8px 8px;
        margin: 3px 0 10px;
        border: 1px solid #f1f1f1;
    }

    input:focus{
        outline: 1px solid white ;
    }

    select{
        width: 100%;
        padding: 8px 8px;
        margin: 3px 0 10px;
        border: 1px solid #f1f1f1;
    }

    select:focus{
        outline: 1px solid white ;
    }

    .btn{
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 10px;
    }

    button{
        background-color: green;
        color: white;
        padding: 5px 30px;
        cursor: pointer;
        font-size: 18px;
        text-transform: capitalize;
        margin-top: 20px;
        border: 1px solid #f1f1f1;
        box-shadow: 0px 0px 1px gold;
        border-radius: 5px;
    }

    button:focus{
        outline: white;
    }

    input[type=checkbox]{
        display: inline-block;
        width: 16px;
        position: relative;
        margin: 0 5px 0 0;
        top: 2px;
    }

    .check{
        font-size: 14px;
        margin-top: 10px;
    }

    .pass{
        color: red;
        font-size: 10px;
        position: relative;
        top: -8px;
        font-style: italic;
    }
</style>