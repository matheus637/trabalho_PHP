# trabalho_PHP
<!-- template.html -->
<ul>
  {% for user in users %}
    <li>{{ user.name }} - {{ user.email }}</li>
  {% endfor %}
# Flask controller
from flask import render_template
users = [{'name': 'Alice', 'email': 'alice@example.com'}, ...]
return render_template("template.html", users=users)
🔹 2. Django Templates
<!-- template.html -->
<ul>
  {% for user in users %}
    <li>{{ user.name }} - {{ user.email }}</li>
  {% endfor %}
</ul>
# views.py
def show_users(request):
    users = User.objects.all()
    return render(request, "template.html", {'users': users})
 Nota: Jinja2 e Django Templates são muito semelhantes, mas o Django inclui proteções automáticas contra XSS e outros filtros embutidos.
3. Vue.js
<!-- App.vue -->
<template>
  <ul>
    <li v-for="user in users" :key="user.id">
      {{ user.name }} - {{ user.email }}
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      users: [
        { id: 1, name: "Alice", email: "alice@example.com" },
        // ...
      ]
    };
  }
}
</script>
➡️ Usa v-for para loops e interpolação com {{ }}. A lógica de dados é separada no script.
🔹 4. React (JSX)
jsx
// Users.js
function Users() {
  const users = [
    { id: 1, name: "Alice", email: "alice@example.com" },
    // ...
  ];
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>
          {user.name} - {user.email}
        </li>
      ))}
    </ul>
  );
}
➡️ Em React, HTML e lógica são combinados via JSX. A estrutura é flexível e declarativa.
🔹 5. Angular
<!-- users.component.html -->
<ul>
  <li *ngFor="let user of users">
    {{ user.name }} - {{ user.email }}
  </li>
</ul>
ts
// users.component.ts
export class UsersComponent {
  users = [
    { name: "Alice", email: "alice@example.com" },
    // ...
  ];
}
➡️ Usa *ngFor como diretiva estrutural. A lógica vive no TypeScript.
🔹 6. Blade (Laravel)
blade
<!-- users.blade.php -->
<ul>
  @foreach ($users as $user)
    <li>{{ $user->name }} - {{ $user->email }}</li>
  @endforeach
</ul>
// Controller
public function showUsers() {
    $users = User::all();
    return view('users', ['users' => $users]);
}

