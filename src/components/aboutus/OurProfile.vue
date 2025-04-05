<template>
    <div class="partner-content">
        <h2>{{title}}</h2>
        <div class="card-container">
            <div
            v-for="(profile, index) in items"
            :key="index"
            class="card"
            >
            <h5 class="profile_name">{{ profile.name }}</h5>
            <br>
            <br v-if="profile.name !='Data Center Maintainance Profile'">
            <button
                @click="downloadPDF(profile)"
                class="card-button"
            >
            <img :src="require('@/assets/images/icon/download_icon.svg')" alt="" />Download PDF
            </button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:{
            items: {
                type: Array
            },
            title: {
                type: String
            }
        },
        methods: {
            downloadPDF(profile) {
            const link = document.createElement("a");
            link.href = profile.file;
            link.setAttribute("download", `${profile.file_name}.pdf`);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
    }
  }
    }
</script>

<style  scoped>

.partner-content {
    margin: 10px auto 50px;
}
.partner-content h2 {
    text-align: center;
    font-size: 30px;
    margin-bottom: 8px;
}
img{
    width: 20px;
}
.card-container {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap; /* Allows wrapping on smaller screens */
  padding: 20px;
  background-color: #f7f6dc;
}

.card {
  width: 250px;
  height: 150px;
  padding: 16px;
  background-color: white;
  border: 1px solid #ddd;
  border-radius: 12px;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.card button {
  padding: 10px 16px;
  background: #7fb773;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s ease-in-out;
}

.card button:hover {
  background: #333;
}



</style>
