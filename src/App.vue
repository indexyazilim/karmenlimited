<template>
  
  <div>
    <video class="karmen-video" src="/assets/flowers.mp4" controls="false" autoplay muted loop/>

    <div class="karmen-video-overlay"></div>
      
    <div class="karmen-content">
      <div class="border">
        <div>
          <div class="karmen-nav">
            <div class="section left">
            </div>
            <div class="section right">
              <span>
                <select class="karmen-lang" v-model="$root.$i18n.locale">
                  <option value="tr">Türkçe</option>
                  <option value="en">English</option>
                </select>
              </span>
            </div>
          </div>
        </div>
        <div class="karmen-cols">  
          <div class="karmen-col stretch">
            
            <KarmenSection
              :link="guidancyURL"
              image="/assets/guidancy-logo.png"
              title="Guidanc'y"
              :subtitle="$t('guidancy-subtitle')"
            />

          </div>
          <div class="separator"></div>
          <div class="karmen-col">
            
            <KarmenSection
              :link="gingerURL"
              image="/assets/gingeristanbul-logo.png"
              title="Ginger"
              :subtitle="$t('ginger-subtitle')"
            />

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import KarmenSection from './components/KarmenSection.vue';

export default {
  name: 'App',
  components: {
    KarmenSection
  },
  computed:{
    locale(){
      return this.$root.$i18n.locale;
    },
    guidancyURL(){
      return 'http://guidancyeventsolutions.com?lang=' + this.locale;
    },
    gingerURL(){
      return 'http://gingeristanbul.com?lang=' + this.locale;
    }
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400&display=swap');

body,html{
  /*background-color:rgb(248,247,239);*/
  height:100%;
  margin:0;
  padding:0;
}

#app{
  height:100%;
}

.border{
  border:10px solid #6b6764;
  padding:18px 24px;
}

.karmen-content{
  position:fixed;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  font-family: 'Raleway', sans-serif;
  background-color:rgb(243, 242, 234);
  border-radius: 6px;
  border:20px solid #c5e5cd;
  box-shadow:0px 2px 6px #777;
}

.karmen-cols{
  display:flex;
  justify-content: center;
}

.karmen-col{
  display:flex;
  align-self: center;
  margin:48px 56px 24px 56px;
}

.separator{
  border-left:10px solid #6b6764;
  border-top:none;
  height:85%;
  width:0;
  position:absolute;
  top:50%;
  left:50%;
  transform: translate(-50%,-50%);
}

.karmen-nav{
  position:relative;
}

.karmen-nav .section.left{
  position:absolute;
  left:0;
}

.karmen-nav .section.right{
  position:absolute;
  right:0;
}

.karmen-lang{
  text-align:left;
  padding:6px 6px;
  border:none;
  border-radius:4px;
  margin:0px;
  background-color:inherit;
  outline: none;
  color:#555;
}

.karmen-video{
  position:fixed;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  z-index:-1000;
  background-color:rgba(0,0,0,0.5)
}

.karmen-video-overlay{
  position:fixed;
  top:0;
  left:0;
  right:0;
  bottom:0;
  z-index:-999;
  background-color:rgba(228,227,219,0.6);
}

@media screen and (max-width: 992px) {
  
  .karmen-content{
    border-width:10px;
    width:90%;
  }

  .karmen-cols{
    flex-direction:column;  
  }

  .karmen-col{
    margin:24px 0;
  }

  .border{
    border-width:5px;
    padding:12px 12px;
  }

  .separator{
    border-width:5px;
    border-left:none;
    width:80%;
    height:0;
    border-top:5px solid #6b6764;
  }

}

</style>
