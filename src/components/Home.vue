/* eslint-disable */
<template>
  <div class="container">
    <h1>Hello</h1>
      <div class="panel panel-default">
        <div class="panel-heading">Dictionaries list</div>
          <div class="panel-body">
            <table class="table table-bordered table-striped">
              <thead>
                <tr>
                  <th>Name</th>
                  <th>Synonym</th>
                  <th>Guid</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="dict of dicts"
                :key="dict.id">
                  <td>{{ dict.name }}</td>
                  <td>{{ dict.synonym }}</td>
                  <td>{{ dict.guid }}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {data() {
        return {
            dicts: []
        };
    },
    mounted() {
        //var app = this;
        axios.get('http://localhost:8000/api/dict/color')
        .then(response => (this.dicts = response.data.items));
    }   
}
</script>

<style>
	
</style>