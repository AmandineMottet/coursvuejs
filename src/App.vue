<template>
  <div class="container">
    <h3>Ma fiche perso</h3>
    <div class="row">
      <div class="col-6">
        <div class="mb-3">
          <label class="form-label" for="lastname">Nom</label>
          <input v-model="lastname" class="form-control" type="text">
        </div>
      </div>
      <div class="col-6">
        <div class="mb-3">
          <label class="form-label" for="firstname">Prénom</label>
          <input v-model="firstname" class="form-control" type="text">
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-6">
        <div class="mb-3">
          <label class="form-label" for="age">Âge</label>
          <input v-model="age" class="form-control" type="number">
        </div>
      </div>
      <div class="col-6">
        <div class="mb-3">
          <label class="form-label" for="gender">Genre</label>
          <select v-model="sex" class="form-control">
            <option value="default" disabled>Selectionner une valeur</option>
            <option value="male">Homme</option>
            <option value="female">Femme</option>
            <option value="other">Autres</option>
          </select>
        </div>
      </div>
    </div>
    <!-- Deuxième  -->
    <hr>
    <h3>Ma fiche perso</h3>
    <div class="row">
      <div class="col-6">
        <div class="mb-3">
          Nom : {{ lastname }}
        </div>
      </div>
      <div class="col-6">
        <div class="mb-3">
          Prénom : {{ firstname }}
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-6">
        <div class="mb-3">
          Âge : {{ formatAge }}
        </div>
      </div>
      <div class="col-6">
        <div class="mb-3">
          Genre : {{ gender }}
        </div>
      </div>
      <!-- Troisième  -->
      <hr>
      <h3>Ma fiche perso</h3>
      <div class="row">
        <div class="col-6">
          <div class="mb-3">
            Nom : {{ lastnamesent }}
          </div>
        </div>
        <div class="col-6">
          <div class="mb-3">
            Prénom : {{ firstnamesent }}
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-6">
          <div class="mb-3">
            Âge : {{ agesent }}
          </div>
        </div>
        <div class="col-6">
          <div class="mb-3">
            Genre : {{ gendersent }}
          </div>
        </div>
      </div>
      <div class="d-flex justify-content-endu">
        <input class="btn btn-outline-secondary" @click="send" type="submit">
      </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lastname: '',
      lastnameDisplay: '',
      firstname: '',
      age: null,
      sex: 'default',
      lastnamesent: '',
      firstnamesent: '',
      agesent: '',
      gendersent: '',
    };
  },
  methods: {
      send(){
        this.lastnamesent = this.lastname;
        this.firstnamesent = this.firstname;
        this.agesent = this.formatAge;
        this.gendersent = this.gender;
      }
  },
  computed: {
    formatAge(){
      if(this.age){
        return this.age + ' ans';
      } return '';
    },
    gender() {
      if (this.sex === 'male') {
        return 'un homme';
      } else if (this.sex === 'female') {
        return 'une femme';
      } else if (this.sex === 'default') {
        return '';
      }
      return "Flaque d'eau";
    }
  }


}


</script>