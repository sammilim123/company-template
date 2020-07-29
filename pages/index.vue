<template>
  <div class="relative">
    <div class="h-screen">
      <div class="flex flex-col">
        <!-- 
          Header Content ( Landing Page )

          PARAMETERS
          :imgURL (URL for Background)
          :header_txt ( Header Text )
          :second_header ( Header 2 Text)
          :descriptions ( Descriptions )
        -->
        <HeaderContent
          imgURL="data:image/jpeg;base64,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"
          header_txt="Iceland by ABC"
          second_header="Beautiful Scenery"
          descriptions="Header Descriptions"
        ></HeaderContent>
        <!-- 
          About Content 

          PARAMETERS
          :imgURL ( URL for about us )
        -->
        <AboutContent
          imgURL="data:image/png;base64,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"
        >
          <template
            v-slot:about
          >ABC company is a travelling agency touring iceland eco-scenery sites.</template>
        </AboutContent>

        <ServiceContent>
          <template v-slot:services>
            <!-- 

              Service 

              PARAMETERS

              :imgURL (image url)
            -->
            <Service imgURL="/img/icon1.png" title="Catalogues">
              <template v-slot:content>Take a look at where we can bring you to</template>
            </Service>

            <Service imgURL="/img/icon2.png" title="Service Title">
              <template
                v-slot:content
              >Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellendus excepturi quisquam temporibus non nisi doloribus cumque cum molestiae odio velit ratione perspiciatis assumenda numquam quam porro, sed quasi quia possimus?</template>
            </Service>

            <Service imgURL="/img/icon3.png" title="Service Title">
              <template
                v-slot:content
              >Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellendus excepturi quisquam temporibus non nisi doloribus cumque cum molestiae odio velit ratione perspiciatis assumenda numquam quam porro, sed quasi quia possimus?</template>
            </Service>

            <Service imgURL="/img/icon4.png" title="Service Title">
              <template
                v-slot:content
              >Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellendus excepturi quisquam temporibus non nisi doloribus cumque cum molestiae odio velit ratione perspiciatis assumenda numquam quam porro, sed quasi quia possimus?</template>
            </Service>
          </template>
        </ServiceContent>

        <!-- 
          Portfolio
        -->
        <PortfolioContent>
          <template v-slot:portfolio>
            <!-- 
              Project

              PARAMETERS
              :imgURL ( img URL for Project )
              :name ( Name of the Project )
              :project ( Name of Project Type)
              :projectURL ( Link Address to project)
            -->
            <Project
              imgURL="https://pbs.twimg.com/profile_images/1157035760085684224/iuxTnT5g_400x400.jpg"
              name="Company template"
              project="NuxtJS app"
              projectURL="https://github.com/sammilim123/company-template"
            />
            <Project
              imgURL="https://pbs.twimg.com/profile_images/1157035760085684224/iuxTnT5g_400x400.jpg"
              name="Company template"
              project="NuxtJS app"
              projectURL="https://github.com/sammilim123/company-template"
            />
          </template>
        </PortfolioContent>
        <ContactContent
          address="Level 11, Menara KEN TTDI, No.37 Jalan Burhanuddin Helmi, Taman Tun Dr. Ismail"
          email="support@thelead.io"
          phone="6016-473 7281"
          imgURL="/img/lead-white-logo.png"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  head() {
    return {
      title: "ABC company"
    };
  }
};
</script>