<template>
  <div class="about-us">
    <div class="header">
      <h5>ABOUT</h5>
      <h2>Your Best IT Partner</h2>
      <h6>Everyone has a story. Here's ours.</h6>
    </div>

    <!-- Image with glassmorphism card -->
    <div class="image-container">
      <img :src="require('@/assets/images/yangon.jpg')" alt="Yangon" />
      <div class="glass-card" :style="glassCardStyle">
      <p class="read-more-text">
        {{ showMore ? fullText : shortText }}
        <span v-if="!showMore">...</span>
        <button @click="showMore = !showMore">
          {{ showMore ? ' Show Less' : ' Read More' }}
        </button>
      </p>

      </div>
    </div>

    <!-- We Are Section -->
    <div class="we-are">
      <h6>We are</h6>
      <div class="items">
        <div class="item" v-for="(trait, index) in traits" :key="index">
          <div class="block">{{ trait.title }}</div>
          <p>{{ trait.description }}</p>
        </div>
      </div>
    </div>

    <!-- Video Section -->
    <div class="aboutus-video">
      <iframe
        src="https://www.youtube.com/embed/pygRoZSd80A?si=WMTHpGivb1Aq06dG"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
    </div>

    <!-- Bottom Text -->
    <div class="about-us-text">
      <h2>A team built on experience</h2>
      <p>
        We're continuing to build our network nationally, bringing together a
        vibrant team with best-in-class service and technical skills alike. With
        the experience of 1K projects we had done in Yangon and Singapore, our
        team is growing fast.
      </p>
    </div>

    <!-- Profiles -->
    <OurProfile :items="profiles" :title="'Our Solution Profiles'" />
  </div>
</template>

<script>
import OurProfile from "./OurProfile.vue";
import { ref, computed } from "vue";

export default {
  components: { OurProfile },
  setup() {
    const showMore = ref(false);
    const fullText = `Green IT Co., Ltd is the leading resource for comprehensive system integration as well as supply the most qualified enterprise networking devices to all sizes of Business across Singapore and Myanmar and was founded in 2015. We supply hardware devices for Computing, Networking, Licensing Software and ELV system. The provided solutions and services are Infrastructure Services, ELV Services & Solutions, Server Rental Services, Collaboration Solutions, Enterprise Solutions, DC Maintenance & Colocation, Network Security Services and Cloud & Cloud PBx Solutions.`;
    const shortText = fullText.slice(0, 100);

    const glassCardStyle = computed(() => ({
      top: showMore.value ? '50%' : '80%',
      left: '50%',
      transform: 'translate(-50%, -50%)',
    }));

    const profiles = [
      { name: 'Company Profile', file: '/pdfs/company_profile.pdf', file_name: 'Green IT Company Profile' },
      { name: 'ELV Profile', file: '/pdfs/elv_profile.pdf', file_name: 'Green IT ELV Profile' },
      { name: 'Solution Profile', file: '/pdfs/solution_profile.pdf', file_name: 'Green IT Solution Profile' },
      { name: 'Licensing Solution', file: '/pdfs/licensing_profile.pdf', file_name: 'Green IT Licensing Software Profile' },
      { name: 'Server Rentals', file: '/pdfs/server_rental_profile.pdf', file_name: 'Green IT Server Rental Profile' },
      { name: 'ERP Profile', file: '/pdfs/erp_profile.pdf', file_name: 'Green IT ERP Profile' },
      { name: 'Data Center Maintainance', file: '/pdfs/data_center.pdf', file_name: 'Green IT Data Center Maintainance Profile' },
    ];

    const traits = [
      { title: 'Passionate', description: 'We are intensely enthusiastic about providing a superior experience' },
      { title: 'Respectful', description: 'We are polite, kind and compassionate to one another, even when it gets tough.' },
      { title: 'Ownership', description: 'We are empowered to do our jobs and work towards a common goal.' },
      { title: 'Unified', description: 'We work as a team and trust each other to create a seamless experience.' },
      { title: 'Reliable', description: 'We are consistently good in quality control, performance, services and can be trusted.' },
    ];

    return { showMore, fullText, shortText, glassCardStyle, profiles, traits };
  },
};
</script>

<style scoped>
.read-more-text {
  font-size: 30px !important;
  line-height: 50px !important;
  margin-bottom: 15px;
  color: white;
}
.read-more-text button {
  background: none;
  border: none;
  color: #007bff;
  text-decoration: underline;
  font-size: 18px;
  cursor: pointer;
  display: inline;
  padding-left: 8px;
}
.about-us {
  padding: 30px 10%;
  font-family: Arial, sans-serif;
}

.header {
  text-align: center;
  margin-bottom: 40px;
}

.header h5 {
  background-color: #7fb773;
  display: inline-block;
  padding: 5px 15px;
  border-radius: 4px;
  color: #fff;
  font-size: 14px;
}

.header h2 {
  font-size: 36px;
  margin: 15px 0 5px;
}

.header h6 {
  font-size: 18px;
  color: #555;
}

.image-container {
  position: relative;
  width: 100%;
  height: 600px;
  overflow: hidden;
  margin-bottom: 40px;
}

.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.glass-card {
  position: absolute;
  width: 80%;
  max-width: 800px;
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  padding: 30px;
  border-radius: 15px;
  color: white;
  font-size: 18px;
  line-height: 30px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.25);
  text-align: center;
  transition: top 0.3s ease;
}

.glass-card p {
  font-size: 25px !important;
  line-height: 50px !important;
  margin-bottom: 15px;
}

.glass-card button {
  background-color: transparent;
  border: none;
  color: white;
  text-decoration: underline;
  font-size: 18px;
  cursor: pointer;
}

.we-are {
  margin-top: 40px;
}

.we-are h6 {
  font-size: 22px;
  margin-bottom: 20px;
}

.items {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.item {
  width: 180px;
  text-align: center;
}

.item .block {
  background-color: #7fb773;
  color: #fff;
  font-size: 20px;
  font-weight: bold;
  padding: 30px 10px;
  border-radius: 8px;
  margin-bottom: 10px;
}

.item p {
  font-size: 16px;
  color: #333;
}

.aboutus-video {
  text-align: center;
  margin: 50px 0;
}

.aboutus-video iframe {
  width: 100%;
  max-width: 960px;
  height: 540px;
}

.about-us-text {
  background: #f7f6dc;
  padding: 50px 10%;
  text-align: center;
}

.about-us-text h2 {
  font-size: 30px;
  margin-bottom: 20px;
}

.about-us-text p {
  font-size: 18px;
  color: #444;
}
@media (max-width: 1200px) {
  .glass-card p {
    font-size: 20px !important;
    line-height: 40px !important;
  }

  .read-more-text {
    font-size: 20px !important;
    line-height: 35px !important;
  }
}

@media (max-width: 768px) {
  .about-us {
    padding: 30px 5%;
  }

  .header h2 {
    font-size: 28px;
  }

  .header h6 {
    font-size: 16px;
  }

  .image-container {
    height: 400px;
  }

  .glass-card {
    width: 90%;
    padding: 20px;
    font-size: 16px;
    line-height: 28px;
  }

  .glass-card p {
    font-size: 18px !important;
    line-height: 30px !important;
  }

  .we-are h6 {
    font-size: 20px;
  }

  .item {
    width: 45%;
  }

  .item .block {
    font-size: 16px;
    padding: 20px 5px;
  }

  .item p {
    font-size: 14px;
  }

  .aboutus-video iframe {
    height: 300px;
  }

  .about-us-text h2 {
    font-size: 24px;
  }

  .about-us-text p {
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  .item {
    width: 100%;
  }

  .glass-card {
    padding: 15px;
  }

  .glass-card p {
    font-size: 16px !important;
    line-height: 28px !important;
  }

  .read-more-text {
    font-size: 16px !important;
    line-height: 28px !important;
  }

  .aboutus-video iframe {
    height: 200px;
  }

  .header h2 {
    font-size: 24px;
  }

  .header h6 {
    font-size: 14px;
  }
}

</style>
