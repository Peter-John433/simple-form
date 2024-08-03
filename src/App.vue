<template>
    <div>
        <div class="app">
          <SectionOne :header="header" />
            <div class="app-two">
               <SectionTwo />
            </div>
        </div>
    </div>
</template>
<script>
  import SectionOne from './components/form-comps/SectionOne.vue'
  import SectionTwo from './components/form-comps/SectionTwo.vue';
  export default{
     name: 'app',
     components:{ SectionOne, SectionTwo },
     data(){
      return{
         header: 'simple form'
      }
     }
  }
</script>
<style scoped>
  .app{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: 30px;
  }

  .app-two{
    width: 450px;
    height: 400px;
    background-color: white;
    margin: 50px 0;
    border-radius: 8px;
    box-shadow: 0px 0px  1px #0d0d0d;
    padding: 20px;
  }

  @media screen and (max-width: 576px) {
        .app{
           padding: 50px 15px 0;
        }
        .app-two{
          width: 100%;
        }
    }
</style>