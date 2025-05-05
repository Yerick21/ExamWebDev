<template>
    <nav>
       <router-link to="/">Home</router-link>
         <router-link to="/plants">Plants</router-link>

         <!-- Add the Select Dropdown  -->
          <select @change="$emit('filter-plants',$event.target.value)">

            <option value="All">All</option>
            <option value="indoor">Indoor</option>
            <option value="outdoor">Outdoor</option>
          </select>
    </nav>
</template>