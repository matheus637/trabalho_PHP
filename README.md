# trabalho_PHP
Jinja2 (Flask)
html
<!-- template.html -->
<ul>
  {% for user in users %}
    <li>{{ user.name }} - {{ user.email }}</li>
  {% endfor %}
</ul>
# app.py (Flask)
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
    users = [
        {"name": "Ana", "email": "ana@email.com"},
        {"name": "João", "email": "joao@email.com"}
    ]
    return render_template("template.html", users=users)
Django Template Engine
<!-- template.html -->
<ul>
  {% for user in users %}
    <li>{{ user.name }} - {{ user.email }}</li>
  {% endfor %}
</ul>
# views.py
from django.shortcuts import render

def index(request):
    users = [
        {"name": "Ana", "email": "ana@email.com"},
        {"name": "João", "email": "joao@email.com"}
    ]
    return render(request, "template.html", {"users": users})
Vue.js (Client-side rendering)
<!-- Vue Component -->
<template>
  <ul>
    <li v-for="user in users" :key="user.email">
      {{ user.name }} - {{ user.email }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      users: [
        { name: "Ana", email: "ana@email.com" },
        { name: "João", email: "joao@email.com" }
      ]
    };
  }
};
</script>
React
// React Component (JSX)
function UserList() {
  const users = [
    { name: "Ana", email: "ana@email.com" },
    { name: "João", email: "joao@email.com" }
  ];

  return (
    <ul>
      {users.map((user) => (
        <li key={user.email}>
          {user.name} - {user.email}
        </li>
      ))}
    </ul>
  );
}

export default UserList;
Angular
<!-- app.component.html -->
<ul>
  <li *ngFor="let user of users">
    {{ user.name }} - {{ user.email }}
  </li>
</ul>
// app.component.ts
export class AppComponent {
  users = [
    { name: 'Ana', email: 'ana@email.com' },
    { name: 'João', email: 'joao@email.com' }
  ];
}
Laravel (Blade)
<!-- users.blade.php -->
<ul>
  @foreach ($users as $user)
    <li>{{ $user['name'] }} - {{ $user['email'] }}</li>
  @endforeach
</ul>
// Controller (Laravel)
public function index()
{
    $users = [
        ['name' => 'Ana', 'email' => 'ana@email.com'],
        ['name' => 'João', 'email' => 'joao@email.com']
    ];

    return view('users', ['users' => $users]);
}
Jinja2 (Python/Flask)
<!-- template.html (Jinja2) -->
<h1>Olá, {{ nome }}!</h1>

<ul>
  {% for item in lista %}
    <li>{{ item }}</li>
  {% endfor %}
</ul>
# app.py
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def home():
    return render_template("template.html", nome="Maria", lista=["Python", "Flask", "Jinja2"])
Django Template Engine
<!-- template.html (Django) -->
<h1>Olá, {{ nome }}!</h1>

<ul>
  {% for item in lista %}
    <li>{{ item }}</li>
  {% endfor %}
</ul>
# views.py
from django.shortcuts import render

def home(request):
    return render(request, "template.html", {"nome": "João", "lista": ["Django", "ORM", "Admin"]})
Vue.js
<!-- template.vue -->
<template>
  <div>
    <h1>Olá, {{ nome }}!</h1>
    <ul>
      <li v-for="item in lista" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nome: "Ana",
      lista: ["Vue", "Reatividade", "Componentes"]
    };
  }
};
</script>
React (JSX)
// App.jsx
import React from "react";

function App() {
  const nome = "Carlos";
  const lista = ["React", "Hooks", "JSX"];

  return (
    <div>
      <h1>Olá, {nome}!</h1>
      <ul>
        {lista.map((item) => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
Angular
<!-- app.component.html -->
<h1>Olá, {{ nome }}!</h1>
<ul>
  <li *ngFor="let item of lista">{{ item }}</li>
</ul>
// app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
})
export class AppComponent {
  nome = "Lucas";
  lista = ["Angular", "TypeScript", "RxJS"];
}
Blade (Laravel - PHP)
<!-- resources/views/template.blade.php -->
<h1>Olá, {{ $nome }}!</h1>

<ul>
  @foreach ($lista as $item)
    <li>{{ $item }}</li>
  @endforeach
</ul>
// Controller
return view('template', ['nome' => 'Pedro', 'lista' => ['Laravel', 'Eloquent', 'Blade']]);










































