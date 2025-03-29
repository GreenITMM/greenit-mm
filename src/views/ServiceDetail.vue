<template>
  <div class="service-detail">
    <div class="banner-img">
      <img class="banner" :src="service.banner_img" alt="" />
    </div>

    <div class="content">
      <div class="title">
        <img class="icon" :src="service.img" alt="" />
        <h2>{{ service.title }}</h2>
      </div>
      <div>
        <div class="content-section">
          <p v-html="service.p"></p>
          <div class="sub-title-container">
            <img :src="service.preview_img" alt="" /> 
            <div>
              <div class="sub-title">
                <h3>{{ service.sub_title_1 }}</h3>
                <div class="list">
                  <div v-for="(item, i) in service.list_one" :key="i">
                    <i class="fa-solid fa-check-double me-5"></i
                    ><span>{{ item }}</span>
                  </div>
                </div>
              </div>
              <hr v-if="service.sub_title_2">
              <div class="sub-title">
                <h3>{{ service.sub_title_2 }}</h3>
                <div class="list">
                  <div v-for="(item, i) in service.list_two" :key="i">
                    <i class="fa-solid fa-check-double me-5"></i
                    ><span>{{ item }}</span>
                  </div>
                </div>
              </div>
              <hr v-if="service.sub_title_3">
              <div class="sub-title" v-if="service.sub_title_3">
                <h3>{{ service.sub_title_3 }}</h3>
                <div class="list">
                  <div v-for="(item, i) in service.list_three" :key="i">
                    <i class="fa-solid fa-check-double me-5"></i
                    ><span>{{ item }}</span>
                  </div>
                </div>
              </div>

              <hr v-if="service.reference_title">
              <div class="sub-title" v-if="service.reference_title">
                <h3>{{ service.reference_title }}</h3>
                <p>{{ service.reference_description }}</p>
                
                <div class="list">
                  <div v-for="(item, i) in service.reference_list" :key="i">
                    <i class="fa-solid fa-check-double me-5"></i
                    ><span>{{ item }}</span>
                  </div>
                </div>
              </div>

            </div>
          </div>
          <!-- erp module start -->
          <div class="erp-container"  v-if="service.erp_title"> 
              <h3 class="title-center padding-top">Services We Provide</h3>
              <div class="getservice-container">
                <div class="get-service bg-white">
                  <img :src="service.erp_image1" alt=""  class="service-image" />
                  <h4 class="title-center">Odoo ERP</h4>
                </div>
                <div class="get-service bg-white">
                  <img :src="service.erp_image2" alt=""  class="service-image" />
                  <h4 class="title-center">SalesForce</h4>
                </div>
                <div class="get-service bg-white">
                  <img :src="service.erp_image3" alt=""  class="service-image" />
                  <h4 class="title-center">Ecommerce</h4>
                </div>
                <div class="get-service bg-white">
                  <img :src="service.erp_image4" alt=""  class="service-image" />
                  <h4 class="title-center">Hospital Management Software</h4>
                </div>
                <div class="get-service bg-white">
                  <img :src="service.erp_image5" alt=""  class="service-image" />
                  <h4 class="title-center">Customized Solutions</h4>
                </div>
              </div>  
          </div>

          <!-- odoo module -->
           <div class="odoo-container"  v-if="service.erp_title">
              <h3>Odoo ERP has the following modules.........</h3>
              <div class="getservice-container">
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image1" alt=""  class="service-image" />
                    <h4 class="title-center">Accounting</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image2" alt=""  class="service-image" />
                    <h4 class="title-center">CRM</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image3" alt=""  class="service-image" />
                    <h4 class="title-center">POS</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image4" alt=""  class="service-image" />
                    <h4 class="title-center">HRM</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image5" alt=""  class="service-image" />
                    <h4 class="title-center">Purchase</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image6" alt=""  class="service-image" />
                    <h4 class="title-center">Sale</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image7" alt=""  class="service-image" />
                    <h4 class="title-center">Inventory</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image8" alt=""  class="service-image" />
                    <h4 class="title-center">Services</h4>
                  </div>
                  <div class="get-service bg-lighter-green">
                    <img :src="service.erp_odoo_image9" alt=""  class="service-image" />
                    <h4 class="title-center">Marketing Automation</h4>
                  </div>
              </div>
              <div class="blank-section">

              </div>
              <div class="getservice-container">
                  <div class="get-service bg-dark-green">
                    <img :src="service.erp_other_odooimage1" alt=""  class="service-image" />
                    <h4 class="title-center">Restaurant</h4>
                  </div>
                  <div class="get-service bg-dark-green">
                    <img :src="service.erp_other_odooimage2" alt=""  class="service-image" />
                    <h4 class="title-center">LMS</h4>
                  </div>
                  <div class="get-service bg-dark-green">
                    <img :src="service.erp_other_odooimage3" alt=""  class="service-image" />
                    <h4 class="title-center">School Management</h4>
                  </div>
                  <div class="get-service bg-dark-green">
                    <img :src="service.erp_other_odooimage4" alt=""  class="service-image" />
                    <h4 class="title-center">Manufacturing</h4>
                  </div>
                  <div class="get-service bg-dark-green">
                    <img :src="service.erp_other_odooimage5" alt=""  class="service-image" />
                    <h4 class="title-center">Project Management</h4>
                  </div>
              </div>
           </div>
          <!-- end odoo module -->
          <!-- erp module -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { onMounted, onUpdated, ref } from "vue";
import { useStore } from "vuex";
export default {
  props: ["slug"],
  setup(props) {
    const store = useStore();
    let service = ref("");
    onMounted(() => {
      window.scrollTo(0, 0);
      store.dispatch("getService", props.slug);
      service.value = store.state.service;
    });

    onUpdated(() => {
      store.dispatch("getService", props.slug);
      service.value = store.state.service;
    });

    return { service };
  },
};
</script>

<style scoped>
.blank-section {
  height: 50px;
}
.service-detail {
  margin-bottom: 30px;
}
.erp-container{
  background-color: #D9D9D9;
  height: auto;
  margin-top: 20px;
  margin-bottom: 20px;
}
.odoo-container{
  background-color: #FFFFFF;
  height: auto;
  margin-top: 20px;
  margin-bottom: 50px;
}

.title-center {
  text-align: center;
}
.padding-top{
  padding-top: 20px;
}
.getservice-container {
  padding: 50px 100px;
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
}
.get-service {
  width: 250px;
  height: 250px;
  border-radius: 10px;
}
.bg-white {
  background-color: #FFFFFF;
}

.bg-lighter-green{
  background-color: #4FB254;
}

.bg-dark-green {
  background-color: #2CCD81;
}
.container h3 h2{
  padding: 30px;
  width: fit-content;
  margin: 0 auto;
}

.service-detail .banner-img {
  padding: 10px 15%;
}

.service-detail .banner {
  filter: brightness(0.7);
}
.service-detail img {
  width: 100%;
  height: 450px;
  object-fit: cover;
}

.getservice-container img{
  height: 200px !important;
  padding: 20px 40px;
}

.service-detail .content {
  padding: 30px 15%;
  margin-top: 30px;
}

.content .title {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 30px;
}
.content .title h2 {
  font-size: 40px;
  margin-top: 10px;
}

.content .erp-title {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 30px;
}

.content .erp-title h2 {
  font-size: 40px;
  margin-top: 67px;
}

.service-detail .content .icon {
  width: 60px;
  height: 60px;
  object-fit: cover;
}

.content .sub-title-container {
  display: flex;
  flex-direction: row-reverse;
  gap: 10px;
  justify-content: space-between;
  margin-top: 50px;
}

.content .content-section p {
  margin-bottom: 30px;
  font-size: 22px;
  text-align: justify;
  margin-top: 50px;
}

.sub-title-container .sub-title {
  margin-bottom: 20px;
}

.sub-title h3 {
  margin-bottom: 15px;
}

.sub-title .list div {
  margin-bottom: 10px;
}

.sub-title .list i {
  color: #287e3d;
}

.sub-title .list span {
  font-size: 20px;
}
.title-center {
  align-items: center;
}
.content .sub-title-container img {
    width: 40%;
    height: 300px;
    object-fit: cover;
  }

@media (max-width: 1630px) {
  .service-detail {
    margin-bottom: 30px;
  }

  .service-detail .banner-img {
    padding: 10px 9%;
  }
  .service-detail img {
    height: 380px;
    margin-top: -15px;
  }

  .service-detail .content {
    padding: 30px 9%;
    margin-top: 30px;
  }

  .content .title {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 30px;
  }
  .content .title h2 {
    font-size: 35px;
    margin-top: 10px;
  }

  .service-detail .content .icon {
    width: 50px;
    height: 50px;
  }

  .content .sub-title-container {
    display: flex;
    flex-direction: row-reverse;
    gap: 10px;
    align-items: center;
  }

  .content .sub-title-container img {
    width: 20%;
    height: 300px;
    object-fit: cover;
  }

  .content .content-section p {
    margin-bottom: 30px;
  }

  .sub-title-container .sub-title {
    margin-bottom: 20px;
  }

  .sub-title h3 {
    margin-bottom: 15px;
    font-size: 22px;
  }

  .sub-title .list div {
    margin-bottom: 10px;
  }

  .sub-title .list i {
    color: #287e3d;
  }
}

@media (max-width: 1320px) {
  .content .sub-title-container img {
    width: 50%;
    height: 300px;
    object-fit: cover;
  }
}

@media (max-width: 1200px) {
  .service-detail .banner-img {
    padding: 10px 3%;
  }

  .content .content-section p {
    font-size: 20px;
  }
  .get-service {
    width: 150px;
    height: 150px;
    border-radius: 10px;
  }
  .getservice-container img{
    height: 120px !important;
    text-align: center;
    padding: 25px 40px;
  }
  .title-center {
    text-align: center;
    font-size: 16px;
  }

}

@media (max-width: 990px) {
  .service-detail img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    filter: brightness(0.7);
  }

  .content .sub-title-container {
    display: flex;
    flex-direction: column-reverse;
    gap: 10px;
    align-items: start;
  }

  .content .sub-title-container img {
    width: 80%;
    height: 300px;
    object-fit: cover;
    margin-top: 30px;
  }

  .content .sub-title-container img .icon{
    width: 80%;
    height: 300px;
    object-fit: cover;
  }
  .get-service {
    width: 120px;
    height: 120px;
    border-radius: 10px;
  }
  .getservice-container img{
    height: 100px !important;
    text-align: center;
    padding: 27px 38px;
  }
  .title-center {
    text-align: center;
    font-size: 14px;
  }

}

@media (max-width: 768px) {
  .service-detail img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    filter: brightness(0.7);
  }
}

@media (max-width: 500px) {
  .service-detail .banner {
    width: 100%;
    height: 200px;
  }
  .content .title h2 {
    font-size: 24px;
    margin-top: 10px;
  }

  .content .erp-title h2 {
    font-size: 20px;
    margin-top: 10px;
  }

  .service-detail .content .icon {
    width: 50px;
    height: 50px;
    object-fit: cover;
  }

  .sub-title h3 {
    margin-bottom: 15px;
    font-size: 20px;
  }
  .getservice-container {
    padding: 40px 22px;
    display: flex
;
    flex-wrap: wrap;
    gap: 10px;
}
  .get-service {
    width: 110px;
    height: 110px;
    border-radius: 10px;
  }
  .getservice-container img{
    height: 100px !important;
    text-align: center;
    padding: 23px 29px;
  }
  .title-center {
    text-align: center;
    font-size: 10px;
  }
}

@media (max-width: 390px) {
  .service-detail .banner {
    height: 140px !important;
    margin-top: -15px;
  }
  .content .title h2 {
    font-size: 20px;
    margin-top: 10px;
  }

  .content .erp-title h2 {
    font-size: 20px;
    margin-top: 10px;
  }

  .service-detail .content .icon {
    width: 40px;
    height: 40px;
    object-fit: cover;
  }

  .sub-title h3 {
    margin-bottom: 15px;
    font-size: 18px;
  }

}
</style>
