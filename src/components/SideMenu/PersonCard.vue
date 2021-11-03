<template>
  <div class="person">
    <div class="person__photo">
      <img :src="person.picture" alt="photo" />
    </div>
    <div class="person__info">
      <div class="person__info-name">{{ person.name }}</div>
      <div class="person__info-about">{{ person.about }}</div>
      <div class="person__info-company">{{ person.company }}</div>
      <div class="person__info-email">
        <div class="person__info-email__btn">
          <a :href="`mailto:${person.email}`">
            <b-icon font-scale="1.3" icon="envelope"></b-icon
          ></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    person: {
      type: Object,
      default: null,
    },
  },
  computed: {
    formatedDate() {
      return this.person.registered;
    },
  },
};
</script>

<style scoped>
.person {
  display: grid;
  grid-template-columns: 160px 1fr;
  grid-gap: 30px;
}

.person__photo img {
  height: 165px;
  width: 165px;
  border-radius: 20px;
}

.person__info {
  display: grid;
  grid-gap: 10px;
}

.person__info-name {
  color: #2d5eee;
  font-weight: 700;
  font-size: 20px;
  letter-spacing: 1px;
}

.person__info-about {
  font-weight: 600;
  font-size: 18px;
}

.person__info-company {
  font-weight: 500;
  font-weight: 16;
  color: #a2a8b1;
  margin-bottom: 20px;
}

.person__info-email__btn {
  width: 35px;
  padding: 5px 5px 3px 5px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #e2ebfd;
}
</style>
