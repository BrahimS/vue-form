<template>
  <div>
   <h2>hello vueJs</h2>
   <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem voluptatum minus ratione consequatur similique sit suscipit, ea voluptas impedit cumque inventore ipsam dolorum sapiente molestias sint quaerat rem assumenda necessitatibus.</p>
      <List 
      itemType="Cities"
      :listItems="['Marrakech', 'Rabat', 'Tanger', 'Asila']" />
      
      <List 
      itemType="Fruit"
      :listItems="cities" />
  
  </div>
</template>

<script>
import List from './List';
import axios from 'axios';
export default {
  data() {
    return {
      cities: []
    };
  },
  components: {List},
  // Vue lifecycle events: 
  created() {
    // fetch data with axios
    axios.get('/cities.json').then(res => {
      this.cities = res.data.items;
      console.log(this.cities);
    })
  }
}
</script>