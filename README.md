# Gerenciartarefas
function gerenciarTarefas(listaDeTarefas, acao) {
    if (acao === "adicionar") {
        let descricao = prompt("Insira uma descrição para a tarefa:");
        if (descricao) {
            listaDeTarefas.push({ descricao: descricao, concluida: false });
            console.log("Tarefa adicionada com sucesso!");
        } else {
            console.log("Descrição inválida. Nenhuma tarefa adicionada.");
        }
    } else if (acao === "remover") {
        listaDeTarefas = listaDeTarefas.filter(tarefa => !tarefa.concluida);
        console.log("Tarefas concluídas removidas com sucesso!");
    } else if (acao === "listar") {
        console.log("Tarefas pendentes:");
        listaDeTarefas.forEach((tarefa, index) => {
            if (!tarefa.concluida) {
                console.log(`${index + 1}. ${tarefa.descricao}`);
            }
        });
    } else {
        console.log("Ação inválida.");
    }

    return listaDeTarefas;
}

// Exemplo de uso
let tarefas = [
    { descricao: "Estudar", concluida: false },
    { descricao: "Fazer exercícios", concluida: true },
    { descricao: "Trabalhar", concluida: false },
];

// Testes
tarefas = gerenciarTarefas(tarefas, "listar");    // Lista pendentes
tarefas = gerenciarTarefas(tarefas, "adicionar"); // Adiciona uma nova
tarefas = gerenciarTarefas(tarefas, "remover");   // Remove concluídas