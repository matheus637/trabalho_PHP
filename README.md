# trabalho_PHP
1. 🐍 Jinja2 (Flask)
html
<h1>Lista de Usuários</h1>

{% if users %}
<table>
  <thead>
    <tr>
      <th>Nome</th><th>Email</th><th>Idade</th><th>Ações</th>
    </tr>
  </thead>
  <tbody>
    {% for user in users %}
    <tr>
      <td>{{ user.name }}</td>
      <td>{{ user.email }}</td>
      <td>{{ user.age }}</td>
      <td>
        <a href="/edit/{{ user.name }}">Editar</a>
        <a href="/delete/{{ user.name }}">Excluir</a>
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% else %}
<p>Nenhum usuário encontrado.</p>
{% endif %}
2. 🐍 Django Template Engine
html
<h1>Lista de Usuários</h1>
{% if users %}
<table>
  <thead>
    <tr>
      <th>Nome</th><th>Email</th><th>Idade</th><th>Ações</th>
    </tr>
  </thead>
  <tbody>
    {% for user in users %}
    <tr>
      <td>{{ user.name }}</td>
      <td>{{ user.email }}</td>
      <td>{{ user.age }}</td>
      <td>
        <a href="{% url 'edit_user' user.name %}">Editar</a>
        <a href="{% url 'delete_user' user.name %}">Excluir</a>
      </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
{% else %}
<p>Nenhum usuário encontrado.</p>
{% endif %}
3. 🔧 Vue.js
html
<template>
  <div>
    <h1>Lista de Usuários</h1>

    <table v-if="users.length">
      <thead>
        <tr>
          <th>Nome</th><th>Email</th><th>Idade</th><th>Ações</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.email">
          <td>{{ user.name }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.age }}</td>
          <td>
            <button @click="editUser(user)">Editar</button>
            <button @click="deleteUser(user)">Excluir</button>
          </td>
        </tr>
      </tbody>
    </table>

    <p v-else>Nenhum usuário encontrado.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [
        { name: 'Alice', email: 'alice@email.com', age: 30 },
        { name: 'Bob', email: 'bob@email.com', age: 25 }
      ]
    };
  },
  methods: {
    editUser(user) {
      console.log('Editando', user);
    },
    deleteUser(user) {
      console.log('Excluindo', user);
    }
  }
};
</script>
4. ⚛️ React (JSX)
jsx
function UserList({ users }) {
  return (
    <div>
      <h1>Lista de Usuários</h1>

      {users.length > 0 ? (
        <table>
          <thead>
            <tr>
              <th>Nome</th><th>Email</th><th>Idade</th><th>Ações</th>
            </tr>
          </thead>
          <tbody>
            {users.map(user => (
              <tr key={user.email}>
                <td>{user.name}</td>
                <td>{user.email}</td>
                <td>{user.age}</td>
                <td>
                  <button onClick={() => console.log("Editando", user)}>Editar</button>
                  <button onClick={() => console.log("Excluindo", user)}>Excluir</button>
                </td>
              </tr>
            ))}
          </tbody>
        </table>
      ) : (
        <p>Nenhum usuário encontrado.</p>
      )}
    </div>
  );
}
5. 🅰️ Angular (TypeScript)
html
<h1>Lista de Usuários</h1>

<table *ngIf="users.length > 0">
  <thead>
    <tr>
      <th>Nome</th><th>Email</th><th>Idade</th><th>Ações</th>
    </tr>
  </thead>
  <tbody>
    <tr *ngFor="let user of users">
      <td>{{ user.name }}</td>
      <td>{{ user.email }}</td>
      <td>{{ user.age }}</td>
      <td>
        <button (click)="editUser(user)">Editar</button>
        <button (click)="deleteUser(user)">Excluir</button>
      </td>
    </tr>
  </tbody>
</table>

<p *ngIf="users.length === 0">Nenhum usuário encontrado.</p>
ts
Copiar
Editar
export class UserListComponent {
  users = [
    { name: 'Alice', email: 'alice@email.com', age: 30 },
    { name: 'Bob', email: 'bob@email.com', age: 25 }
  ];

  editUser(user: any) {
    console.log('Editando', user);
  }

  deleteUser(user: any) {
    console.log('Excluindo', user);
  }
}
6. 🐘 Blade (Laravel)
blade
<h1>Lista de Usuários</h1>

@if(count($users) > 0)
<table>
  <thead>
    <tr>
      <th>Nome</th><th>Email</th><th>Idade</th><th>Ações</th>
    </tr>
  </thead>
  <tbody>
    @foreach ($users as $user)
    <tr>
      <td>{{ $user['name'] }}</td>
      <td>{{ $user['email'] }}</td>
      <td>{{ $user['age'] }}</td>
      <td>
        <a href="{{ route('users.edit', $user['name']) }}">Editar</a>
        <a href="{{ route('users.delete', $user['name']) }}">Excluir</a>
      </td>
    </tr>
    @endforeach
  </tbody>
</table>
@else
<p>Nenhum usuário encontrado.</p>
@endif
✅ Jinja2 / Django
html
{% for user in users %}
  <p>{{ forloop.counter }}. {{ user.name }}
    {% if user.age >= 18 %}
      (Adulto)
    {% else %}
      (Menor de idade)
    {% endif %}
  </p>
{% endfor %}
✅ Vue.js
html
<p v-for="(user, index) in users" :key="user.email">
  {{ index + 1 }}. {{ user.name }}
  <span v-if="user.age >= 18">(Adulto)</span>
  <span v-else>(Menor de idade)</span>
</p>
✅ React
jsx
{users.map((user, index) => (
  <p key={user.email}>
    {index + 1}. {user.name}{" "}
    {user.age >= 18 ? "(Adulto)" : "(Menor de idade)"}
  </p>
))}
✅ Angular
html
<p *ngFor="let user of users; index as i">
  {{ i + 1 }}. {{ user.name }}
  <span *ngIf="user.age >= 18">(Adulto)</span>
  <span *ngIf="user.age < 18">(Menor de idade)</span>
</p>
✅ Blade (Laravel)
blade
@foreach ($users as $index => $user)
  <p>{{ $index + 1 }}. {{ $user['name'] }}
    @if ($user['age'] >= 18)
      (Adulto)
    @else
      (Menor de idade)
    @endif
  </p>
@endforeach
🔹 2. Inclusão de outro template / componente parcial
✅ Jinja2 / Django
html
<!-- base.html -->
<html>
  <body>
    {% block content %}{% endblock %}
  </body>
</html>

<!-- user_list.html -->
{% extends "base.html" %}
{% block content %}
  {% include "user_row.html" with user=users.0 %}
{% endblock %}
✅ Vue.js
html
<!-- UserRow.vue -->
<template>
  <tr><td>{{ user.name }}</td></tr>
</template>

<!-- UserList.vue -->
<UserRow v-for="u in users" :key="u.email" :user="u" />
✅ React
jsx
function UserRow({ user }) {
  return <tr><td>{user.name}</td></tr>;
}

function UserList({ users }) {
  return (
    <>
      {users.map(user => <UserRow key={user.email} user={user} />)}
    </>
  );
}
✅ Angular
html
<!-- user-row.component.html -->
<tr><td>{{ user.name }}</td></tr>

<!-- user-list.component.html -->
<app-user-row *ngFor="let u of users" [user]="u"></app-user-row>
✅ Blade
blade
<!-- user-row.blade.php -->
<tr><td>{{ $user['name'] }}</td></tr>

<!-- main.blade.php -->
@foreach($users as $user)
  @include('user-row', ['user' => $user])
@endforeach
🔹 3. Formulário simples
✅ Jinja2 / Django
html
<form method="post">
  Nome: <input type="text" name="name" value="{{ user.name }}">
  Idade: <input type="number" name="age" value="{{ user.age }}">
  <button type="submit">Salvar</button>
</form>
✅ Vue.js
html
<form @submit.prevent="save">
  <input v-model="user.name" type="text" placeholder="Nome" />
  <input v-model="user.age" type="number" />
  <button type="submit">Salvar</button>
</form>
✅ React
jsx
<form onSubmit={handleSubmit}>
  <input
    type="text"
    value={user.name}
    onChange={e => setUser({ ...user, name: e.target.value })}
  />
  <input
    type="number"
    value={user.age}
    onChange={e => setUser({ ...user, age: e.target.value })}
  />
  <button type="submit">Salvar</button>
</form>
✅ Angular
html
<form (ngSubmit)="save()" #userForm="ngForm">
  <input [(ngModel)]="user.name" name="name" />
  <input [(ngModel)]="user.age" name="age" type="number" />
  <button type="submit">Salvar</button>
</form>
✅ Blade (Laravel)
blade
<form method="POST" action="/users/save">
  @csrf
  <input type="text" name="name" value="{{ old('name', $user['name']) }}">
  <input type="number" name="age" value="{{ old('age', $user['age']) }}">
  <button type="submit">Salvar</button>
</form>
🔹 4. Componente reutilizável (mais claro no client-side)
✅ Vue
vue
<!-- UserCard.vue -->
<template>
  <div class="card">
    <h3>{{ user.name }}</h3>
    <p>{{ user.email }}</p>
  </div>
</template>

<script>
export default {
  props: ['user']
};
</script>
✅ React
jsx
function UserCard({ user }) {
  return (
    <div className="card">
      <h3>{user.name}</h3>
      <p>{user.email}</p>
    </div>
  );
}
✅ Angular
html
<!-- user-card.component.html -->
<div class="card">
  <h3>{{ user.name }}</h3>
  <p>{{ user.email }}</p>
</div>

<!-- Usage -->
<app-user-card [user]="u"></app-user-card>


