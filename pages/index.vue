<template>
  <div class = "flex h-screen bg-gray-700">
    <div class = "m-auto w-full px5 md:w-1/3">
      <div class = "pl-1 text-white font-medium text-2xl, tracking wide text-center">
        Inventory system{{email}}
       </div> 
    <form>
      <div class = "my-2">
      <inputElement
        :labelName = "'Email'"
        :labelId = "'email'"
        :inputType = "'email'"
        :model = "'email'"
        @input = "email = $event"
        :disabled = "false"
      />
      </div>
      <div class = "my-2">
      <inputElement
        :labelName = "'Password'"
        :labelId = "'password'"
        :inputType = "'password'"
        :model = "'password'"
        @input = "password = $event"
        :disabled = "false"
      />
      </div>
      <button @click = "login" class="
           transition
           duration-500
           ease-in-out
           bg-blue-600
           rounded-xs
           w-full
           py-3
           text-white
           font-sans
           font-bold
           tracking-wide
           hover:bg-blue-700
           hover:text-gray-400
           active:outline-none
           focus:outline-none
      ">SIGN IN</button>
    </form>
    </div>  
  </div>
</template>

<script>
import InputElement from '~/components/items/Input.vue';
import Logo from  '~/components/items/Logo.vue';

export default{
  transition:{
    name:"inventory",
    mode:"out-in",
    duration:{enter:1000, leave:500},
    enterActiveClass:"animated fadeIn",
    leaveActiveClass:"animated fadeOut"
  },
  components:{
    Logo,
    InputElement
  },
  data:function(){
    return{
      email:"",
      password:""
    }
  },
  methods:{
    login:function(){
      this.$router.push("/dashboard")
    }
  }
}

</script>
