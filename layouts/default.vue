<template>
  <div class="flex flex-col h-screen w-screen">
    <!--
      Navigation Bar

      PARAMETERS
      :logoURL  (URL for Logo)
     -->
    <NaviWrapper
      imgURL="https://www.jdfulwiler.com/wp-content/uploads/2017/08/abc-company-test-logo.png"
      ></NaviWrapper>

    <div class='flex-1'>
      <div class='flex'>
        <Nuxt class="w-full h-screen overflow-y-auto" />
      </div>
    </div>
    <FooterWrapper />
  </div>
</template>
<script>
export default {
}
</script>