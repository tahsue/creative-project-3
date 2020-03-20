<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form class="pure-form">
        <i class="search-name"><p>NAME: </p></i><input v-model="searchText" />
      </form>
    </div>
  </div>
  <ApplicantList :applicants="applicants" />
</div>
</template>

<script>
// @ is an alias to /src
import ApplicantList from "../components/applicant_list.vue"
export default {
  name: 'Home',
  components: {
    ApplicantList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    applicants() {
      return this.$root.$data.applicants.filter(applicant => (applicant.first_name.toLowerCase() + ' ' + applicant.last_name.toLowerCase()).search(this.searchText) >= 0);
    }
  },
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
  margin-bottom: 50px;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  height: 40px;
  width: 99%;
}

</style>