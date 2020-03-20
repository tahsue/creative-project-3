<template>
<div class="wrapper">
  <div class="applicants">
    <div class="applicant" v-for="applicant in applicants" :key="applicant.id">
      <div class="info">
        <div class="avatar">
            <img :src="applicant.avatar_big">
        </div>
        <div class="name">
            <p><b>Name:</b> {{applicant.first_name}} {{applicant.last_name}}</p>
        </div>
        <div class="personal-info">
            <p><b>Email:</b> {{applicant.email}}</p>
            <p><b>Default Gender:</b> {{applicant.gender}}<p>
            <p><b>Native Culture:</b> {{applicant.race}}</p>
            <p>Manufactured in {{applicant.hometown}}</p>
            <button class="auto" @click="viewProfile(applicant)">View Emplyee Profile</button>
        </div> 
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ApplicantList',
  props: {
    applicants: Array
  },
  methods: {
      viewProfile(applicant) {
          console.log(applicant.id);
          this.$root.$data.applicant = applicant;
          this.$router.push('/profile') 
      }
  }
}
</script>

<style scoped>
html, body, .info { height: 100%; margin: 0; }

.wrapper {
    margin-left: 20px;
    margin-right: 20px;
}

.applicants {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 20px;
    margin-left: 20px;
}

.applicant {
    max-width: 100%;
    border: black solid 1px;
    padding: 20px;
    max-height: 200px;
    margin-top: 20px;
    margin-bottom: 20px;
    background-color: #BFD4DC;
}

button {
  height: 40px;
  width: 250px;
  background: #6D97A2;
  border: black 1px solid;
  font-size: 20px;
  color: white;
  border: none;
}

.info * { 
 position: relative;
}

img {
    border: black solid 1px;
    height: 150px;
    width: 150px;
    background-color: white;
}

.info {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-areas: "avatar personal-info personal-info ." "name personal-info personal-info ." ". . . .";
}

.avatar { 
    grid-area: avatar; 
    
}

.name { grid-area: name; }

.personal-info { 
    grid-area: personal-info; 
    text-align: left;
}

@media (max-width: 1200px) {
  .applicants {
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 20px;
    margin-left: 20px;
}
}

</style>