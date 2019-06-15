<template>
    <div>
        HELLO MAIN
        <div class="side-menu">
            <div class = "menu-container">
                <div class="menu-item">
                    <!-- <img src="@/assets/sample.svg"> -->
                    <div class="text">
                        Sample Text
                    </div>
                </div>
            </div>
        </div>
    </div>

    
</template>

<script>
export default {
  name: 'MainContent',
  props: {
    msg: String
  },
  data:{
      isMenuActive: boolean
  },
  methods:{
      toggleMenu(){
          this.isMenuActive = !this.isMenuActive;
      }
  }
}
</script>

<style lang="scss">

    .side-menu{
        width: 100%;
        height: 100vh;
        background: navy;
        .menu-container{
            .menu-item{
                img{

                }
                .text{

                }
            }
        }
    }

</style>
