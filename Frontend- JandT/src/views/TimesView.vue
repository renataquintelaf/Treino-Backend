<script>
import axios from "axios";
export default {
  data() {
    return {
      times: [],
      novo_time: "",
    };
  },
};
async created(){
  const times = await axios.get("http://localhost:4000/times")
}
methods {
  async salvar(){
    const time={
      nome:this.novo_time,
    };
    const time_criado=await axios.post("http://localhost:4000/times")
    this.times.push(time_criado.data);
  }
}
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" @keydown.enter="salvar" />
      <button @click="salvar">Salvar</button>
    </div>

    <div class="list-times">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.nome }}</td>
            <td>
              <button>Editar</button>
              <button @click="excluir(time)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<style>
.title {
  text-align: center;
  margin: 2rem 0;
  font-size: 150%;
}

.form-input {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 2rem 0;
  border-radius: 30px;
  padding: 2rem;
}
.form-input input {
  width: 80%;
  padding: 0.5rem;
  border-radius: 10px;
  background-color: #a67794;
  border: transparent;
}

.form-input button {
  background-color: rgb(166, 119, 148);
  border-radius: 20%;
}
input,
button {
  padding: 0.6rem;
  border: transparent;
}

.list-times {
  display: flex;
  justify-content: center;
}

table {
  width: 50%;
  border-collapse: collapse;
  margin: 0 auto;
  border: transparent;
  font-size: 1rem;
  text-align: center;
}

table thead {
  background-color: rgb(166, 119, 148);
  color: white;
}
</style>
