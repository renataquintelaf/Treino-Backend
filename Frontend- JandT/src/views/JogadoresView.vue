<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      jogadores: [
        {
          id: "019da1a7-1270-413a-9564-bfa8774fcb88",
          nome: "Jogador 1",
          time: "Time 1",
        },
        {
          id: "7752ad37-d031-4684-98b7-50a42c5b7159",
          nome: "Jogador 2",
          time: "Time 2",
        },
        {
          id: "171e9ba3-0bb3-492e-ba01-429a64cdc252 ",
          nome: "Jogador 3",
          time: "Time 3",
        },
      ],
      novo_jogador: "",
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.jogadores.push({
        id: novo_id,
        nome: this.novo_jogador,
        time: this.novo_time,
      });
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Times</h2>
    </div>
    <div class="form-input">
      <div class="input-um">
        <input type="text" v-model="novo_jogador" />
      </div>
      <div class="input-dois">
        <input type="text" v-model="novo_time" />
      </div>
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-times">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Time.id</th>
            <th>Ações</th>
          </tr>
        </thead>

        <tbody>
          <tr v-for="jogador in jogadores" :key="jogador.id">
            <td>{{ jogador.id }}</td>
            <td>{{ jogador.nome }}</td>
            <td>{{ jogador.time }}</td>
            <td>???</td>
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
  border-radius: 20px;
}
.form-input input {
  width: 80%;
  padding: 0.5 rem;
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
  width: 80%;
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
table tbodyyr:tr:nth-child(odd) {
  background-color: aliceblue;
}
.input-um {
  padding-right: 0.1rem;
  width: 20%;
}
.input-dois {
  padding-left: 0.1rem;
  width: 20%;
}
</style>
