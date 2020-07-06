<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <div id="ggjjkk"></div>
  </div>
</template>

<script>
/* eslint-disable */
import HelloWorld from './components/HelloWorld.vue'
import vueCELoader from "@spectrio/codigo.ce"
import $ from 'jquery'
export default {
  name: 'App',
  components: {
    HelloWorld
  },
   mounted:function(){
    window.VueCELoader = new vueCELoader({
        canUseNewEditor:true,
        showShutterStock:true,
        isAgreedForNewCE :true,
        isNewContent:false,
        isScheduled:false,
        isSA: 'True' == 'True',
        canUseVideoBackgrounds :true,
        hasParameters: false,
        videoExportAvailable:true,
        loaded: false,
        //baseAddress: `//${window.location.host}`,
        cropImageUrl: `//${window.location.host}/ContentWork/CropImageJson/`,
        cropParameters: function () {
            return { contentId: 2836 }
        },
        myAssetsURL: `//${window.location.host}/ContentWork/GetAssetsThumbnailJson`,
        vaultAssetsURL: `//${window.location.host}/ContentWork/GetAssetsThumbnailJson`,
        assetParameters: function () {
            return {
                VaultIds: [1,2],
                VaultItemIds: [],
                ActiveCompanyId: 1
            }
        },
        uploadAssetUrl: `//${window.location.host}/contentwork/uploadnew?library=asset`,
        saveUrl: `//${window.location.host}/ContentWork/SaveHtmlMedia`,
        saveParameters: function () { //additional parameters required for save method
            return {
                Id: 213,
            }
        },
        parameters: [],
        customFonts: [],
        checkBeforeSaveFn: function () { return true; },
        checkAfterSaveFn: null,
        showFeatures:true,
        showSpectrioAssets:true,
        showMyAssets:true
    });

    setTimeout(()=>{
        window.VueCELoader.openFile('paulas testo','../public/paulas_testo/index.html', 'ggjjkk');
    },3000)
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
