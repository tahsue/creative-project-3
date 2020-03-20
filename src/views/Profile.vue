<template>
    <div class="wrapper">
        <div class="name">{{ this.$root.$data.applicant.first_name }} {{ this.$root.$data.applicant.last_name }}</div>
        <hr>
        <div class="info">
            <div class="avatar">
                <img :src="this.$root.$data.applicant.avatar_big">
            </div>
            <div class="qualifications">
                <h2>Qualifications: </h2>
                <p><b>Education:</b> {{ this.$root.$data.applicant.education }} </p>
                <p><b>Previous Function:</b> {{ this.$root.$data.applicant.occupation }} </p>
                <p><b>Specialty:</b> {{ this.$root.$data.applicant.skill }} </p>
            </div>
            <div class="id">
                <h2>Identity Presets: </h2>
                <p><b>Default Gender:</b> {{ this.$root.$data.applicant.gender }} </p>
                <p><b>Native Culture:</b> {{ this.$root.$data.applicant.race }} </p>
            </div>
            <div class="contact_info">
                <h2>Contact Info: </h2>
                <p><b>Email:</b> {{ this.$root.$data.applicant.email }} </p>
                <p><b>Location:</b> {{ this.$root.$data.applicant.address }} </p>
                <p>Manufactured in {{ this.$root.$data.applicant.hometown }} </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    computed: {
        showProfile() {
            return this.$root.$data.applicant;
        }
    } 
}
</script>

<style scoped>

img {
    border: solid black 2px;
    background-color: white;
}

.wrapper {
    display: grid;
    justify-items: center;
}

.info {
    display: flex;
    justify-content: space-around;
}

.name {
    font-size: 40px;
}

html, body, .info { height: 100%; margin: 0; }

h2 {
    text-align: left;
    padding-left: 20px;
}

p {
    text-align: left;
    padding-left: 20px;
}

.info {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-areas: "avatar  qualifications" "avatar id" "avatar contact_info";
}

.avatar { 
    grid-area: avatar;     
}

.qualifications { grid-area: qualifications; }

.id { grid-area: id; }

.contact_info { grid-area: contact_info; }


</style>