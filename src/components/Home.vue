<template>
  <section>
    <div class="CompanieList">
      <a
        v-for="companie in companies"
        :href="companie.website"
        class="CompanieList__item"
        target="_blank"
      >
        <img class="CompanieList__image" :src="`/static/companies/images/${companie.logo}`" :alt="companie.name">
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'home',
  data() {
    return {
      companies: [],
    };
  },
  created() {
    axios.get('/static/companies/companies.json')
      .then(({ data }) => {
        this.companies = this.shuffleArray(data.companies);
      });
  },
  methods: {
    shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        let j = Math.floor(Math.random() * (i + 1));
        let temp = array[i];
        array[i] = array[j];
        array[j] = temp;
      }
      return array;
    },
  },
};
</script>


<style>
  .CompanieList {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding-top: 24px;
  }

  .CompanieList__item:hover {
    transform: scale(1.1);
    box-shadow: 0 12px 48px rgba(0, 0, 0, 0.1);
    z-index: 2;
  }
  .CompanieList__item {
    width: 300px;
    height: 300px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #fff;
    margin: 6px;
    transition: all 0.3s;
  }

  .CompanieList__image {
    max-width: 200px;
    max-height: 140px;
  }
</style>
