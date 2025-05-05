# Fila-e-Pilha

// ===== CLASSES =====

class FilaDeAtendimento {
  constructor() {
    this.fila = [];
  }

  adicionar(aluno) {
    this.fila.push(aluno);
    console.log(`${aluno} foi adicionado à fila.`);
  }

  atender() {
    if (this.fila.length === 0) {
      console.log("Fila vazia.");
    } else {
      const atendido = this.fila.shift();
      console.log(`${atendido} foi atendido.`);
    }
  }

  proximo() {
    if (this.fila.length === 0) {
      console.log("Fila vazia.");
    } else {
      console.log(`Próximo aluno: ${this.fila[0]}`);
    }
  }

  mostrar() {
    if (this.fila.length === 0) {
      console.log("Fila vazia.");
    } else {
      console.log("Fila atual:", this.fila.join(", "));
    }
  }
}

class PilhaDeDocumentos {
  constructor() {
    this.pilha = [];
  }

  adicionar(documento) {
    this.pilha.push(documento);
    console.log(`Documento "${documento}" adicionado.`);
  }

  resolver() {
    if (this.pilha.length === 0) {
      console.log("Pilha vazia.");
    } else {
      const resolvido = this.pilha.pop();
      console.log(`Documento "${resolvido}" resolvido.`);
    }
  }

  topo() {
    if (this.pilha.length === 0) {
      console.log("Pilha vazia.");
    } else {
      console.log(`Documento no topo: ${this.pilha[this.pilha.length - 1]}`);
    }
  }

  mostrar() {
    if (this.pilha.length === 0) {
      console.log("Pilha vazia.");
    } else {
      console.log("Documentos pendentes:", this.pilha.join(", "));
    }
  }
}

// ===== SIMULAÇÃO =====

const fila = new FilaDeAtendimento();
const pilha = new PilhaDeDocumentos();

console.log("\n Sistema\n");

// Fila de Atendimento
fila.adicionar("Alice");
fila.adicionar("Bruno");
fila.adicionar("Carla");

fila.proximo();      // Deve mostrar Alice
fila.atender();      // Atende Alice
fila.mostrar();      // Bruno, Carla
fila.atender();      // Atende Bruno
fila.proximo();      // Deve mostrar Carla

// Pilha de Documentos
pilha.adicionar("Relatório de Notas");
pilha.adicionar("Contrato de Estágio");
pilha.topo();        // Deve mostrar Contrato de Estágio
pilha.resolver();    // Remove Contrato de Estágio
pilha.mostrar();     // Mostra Relatório de Notas
pilha.resolver();    // Remove Relatório de Notas
pilha.resolver();    // Pilha vazia

// ===== ESTADO FINAL =====

console.log("\n ESTADO FINAL:");
console.log("Fila de Atendimento:");
fila.mostrar();
console.log("Pilha de Documentos:");
pilha.mostrar();
