<template>
  <div>
   <h2>hello vueJs</h2>
   <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem voluptatum minus ratione consequatur similique sit suscipit, ea voluptas impedit cumque inventore ipsam dolorum sapiente molestias sint quaerat rem assumenda necessitatibus.</p>
  
      <List 
      itemType="CITY"
      :listItems="['Marrakech', 'Rabat', 'Tanger', 'Asila']" />
      
      <List 
      itemType="FRUIT"
      :listItems="['Orange', 'Pomme', 'Bananne', 'Poire']" />
  
  </div>



</template>

<script>
import List from './List';
export default {
  components: {List}
}
</script>