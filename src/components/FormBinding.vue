<script>
export default {
  name: 'FormBinding',
  data() {
    return {
      title: '',
      emoji: '',
      apreciacion: '',
      competencias: [],
      opinion: '',
      image: {
        src: 'https://cdn3.emoji.gg/emojis/1261-hackerbongocat.gif'
      }
    }
  }
}
</script>

<template>
  <div class="d-flex gap-5">
    <!--Aqui va el formulario-->
    <form>
      <div class="row mb-3">
        <label for="title" class="col-sm-2 col-form-label">Título:</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="title" v-model="title" />
        </div>
      </div>
      <div class="row mb-3">
        <label for="emoji" class="col-sm-2 col-form-label">Emoji:</label>
        <div class="col-sm-3">
          <select class="form-select" id="emoji" v-model="emoji">
            <option selected>Selecciona un emoji</option>
            <option value="👩🏻‍💻">👩🏻‍💻</option>
            <option value="🤓">🤓</option>
            <option value="🤡">🤡</option>
          </select>
        </div>
      </div>
      <fieldset class="row mb-3">
        <legend class="col-form-label col-sm-2 pt-0 me-2">Apreciación:</legend>
        <div class="col-sm-10">
          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="regular"
              value="regular"
              v-model="apreciacion"
            />
            <label class="form-check-label" for="regular"> Regular </label>
          </div>

          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="bien"
              value="bien"
              v-model="apreciacion"
            />
            <label class="form-check-label" for="bien"> Bien </label>
          </div>

          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="muy-bien"
              value="muy bien"
              v-model="apreciacion"
            />
            <label class="form-check-label" for="muybien"> Muy Bien </label>
          </div>

          <div class="form-check form-check-inline">
            <input
              class="form-check-input"
              type="radio"
              name="gridRadios"
              id="increible"
              value="increíble✨"
              v-model="apreciacion"
            />
            <label class="form-check-label" for="increible"> Increíble </label>
          </div>
        </div>
      </fieldset>
      <div class="row mb-3">
        <label for="competencias" class="col-sm-2 col-form-label me-2">Competencias:</label>
        <div class="col-sm-10">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              v-model="competencias"
              value="Morfología de un Componente"
            />
            <label class="form-check-label"> Morfología de un Componente </label>
          </div>

          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              v-model="competencias"
              value="One way y Two way data binding"
            />
            <label class="form-check-label"> One way y Two way data binding </label>
          </div>

          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              v-model="competencias"
              value="El patrón del diseño MVVM"
            />
            <label class="form-check-label"> El patrón del diseño MVVM </label>
          </div>

          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              v-model="competencias"
              value="Directivas"
            />
            <label class="form-check-label"> Directivas </label>
          </div>

          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              v-model="competencias"
              value="Estados"
            />
            <label class="form-check-label"> Estados </label>
          </div>
        </div>
      </div>
      <div class="row mb-3">
        <label for="opinion" class="col-sm-2 col-form-label">Opinión</label>
        <div class="col-sm-10">
          <textarea class="form-control" id="opinion" rows="3" v-model="opinion"></textarea>
        </div>
      </div>
    </form>
    <!--Aqui va la otra cosa-->
    <div class="col-md-6">
      <h1 class="title">
        {{ title }} <span class="emoji">{{ emoji }}</span>
      </h1>
      <h2>Y me parece {{ apreciacion }}</h2>
      <h3>He aprendido:</h3>
      <p class="p-bold">{{ competencias.join(', ') }}.</p>
      <h4>Mi opinión hasta ahora del framework:</h4>
      <p>{{ opinion }}</p>
      <div>
        <img v-bind="image" />
      </div>
    </div>
  </div>
</template>

<style scoped>
form {
  background-color: #784ba0;
  color: white;
  padding: 20px;
  border-radius: 10px;
}

.emoji {
  font-size: xx-large;
}

.title {
  font-size: 2rem;
  color: #784ba0;
  text-decoration: underline;
}

h2 {
  font-size: 1.5rem;
}

.p-bold {
  font-weight: 500;
}
p {
  font-size: 1.2rem;
}

input[type='checkbox']:checked {
  background-color: #bb8aeb;
  border-color: #bb8aeb;
}

input[type='radio']:checked {
  background-color: #bb8aeb;
  border-color: #bb8aeb;
}
</style>
