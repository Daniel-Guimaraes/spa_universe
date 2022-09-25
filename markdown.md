<!-- Quando eu estruturo um objeto com o nome sendo uma string, eu preciso usar um parênteses para pegar esse objeto  -->

const routes = {
"/": "/pages/home.html",
"/about": "/pages/about.html",
"/contact": "/pages/contact.html",
404: "/pages/404.html",
};

console.log(routes['/about'])

---

<!-- Sempre que eu quiser referenciar uma função dentro de uma classe eu uso a proprieade 'this' -->

class Router {
route(event) {
event = event || window.event;
event.preventDefault();

    window.history.pushState({}, "", event.target.href);
    this.handle();

}

handle() {
const pathname = window.location.pathname;
const route = routes[pathname] || routes[404];

    fetch(route)
      .then((data) => data.text())
      .then((html) => {
        document.querySelector("#app").innerHTML = html;
      });

}
}

<!-- Update vscode -->

sudo apt update
sudo apt-get upgrade code

<!-- Conceito de herança em POO -->

class Passaro {
voar() {
alert('voar')
}
}

class Pato extends Passaro {
constructor() {
super()
}
}

const pato = new Pato()
pato.voar()

<!-- Poliformismo em POO -->

class Passaro {
voar() {
alert('Todo passaro pode voar')
}
}

class Pato extends Passaro {
constructor() {
super()
}

voar() {
alert('Menos o pato')
}
}

<!-- como abrir um servidor com o node  -->

- npm init -y
- npm install lite-server
- Entrar no 'package.json' e alterar a propriedade 'scripts' para:
  - "start": "lite-server"
- npm start
