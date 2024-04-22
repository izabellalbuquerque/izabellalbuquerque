// Jogo de Adivinhação em JavaScript

// Gera um número aleatório entre 1 e 10
const numeroAleatorio = Math.floor(Math.random() * 10) + 1;

// Número de tentativas
let tentativas = 3;

// Função para validar a entrada do usuário
function validarEntrada(numero) {
    if (isNaN(numero) || numero < 1 || numero > 10) {
        return false;
    }
    return true;
}

// Função principal do jogo
function jogar() {
    while (tentativas > 0) {
        // Solicita ao usuário um número
        const entrada = prompt(`Digite um número entre 1 e 10. Tentativas restantes: ${tentativas}`);

        // Converte a entrada para número inteiro
        const numeroUsuario = parseInt(entrada);

        // Verifica se a entrada é válida
        if (validarEntrada(numeroUsuario)) {
            // Verifica se o número está correto
            if (numeroUsuario === numeroAleatorio) {
                alert('Parabéns! Você acertou o número.');
                return;
            } else {
                alert('Número errado. Tente novamente.');
                tentativas--;
            }
        } else {
            alert('Entrada inválida. Digite um número entre 1 e 10.');
        }
    }

    // Se o usuário usou todas as tentativas
    alert(`Suas tentativas acabaram. O número era ${numeroAleatorio}.`);
}

// Inicia o jogo
jogar();

