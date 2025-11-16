# Vetores

### Exercício sobre vetores

Na aula de Hoje, Vamos Rever alguns dos exercicios com foco não apenas em vetores, mas tambem com todas as estruturas vistas até o momento 



------------------------------------------------------------------



Reservamos 3 Exercícios onde vocês vão aplicar tudo o que foi ensinado até o momento.

# Exercício de Numero 1 (Ordene os números)

Na programação, existem divesras maneiras de ordenar uma sequencia de números, eles são chamados de "Algoritmos de ordenação".

Vamos fazer a implementação de um desses algortimos

Código:

    // variavel de numeros digitados, 5 no total
    int[] numerosdigitados = new int[5];
    
    // 1. preencha abaixo os valores para que o for funcione corretamente
    for (int i = /*valro inicial*/ ; i < /*tamanhdo do vetor (obs: não coloque o numero diretamente*/; i++)
    {
        // solicite o numero e armazene na variavel numerosdigitados na posição i
        Console.WriteLine("Digite o " + (i + 1) + "º numero: ");
    
        // armazene o valor digitado na posição i do vetor
        numerosdigitados[/*qual posição deve ser lida aqui?*/] = int.Parse(Console.ReadLine());
    }
    
    
    // 2. Lógica da ordenação dos números (sem imprimir nada ainda)
    for (int i = 0; i < numerosdigitados.Length; i++)
    {
        // mais uma repetição para comparar os números
        for (int j = 0; j < numerosdigitados.Length; j++)
        {
            // se o número da posição i for menor que o da posição j, troque-os de lugar
            if (numerosdigitados[i] < numerosdigitados[j])
            {
                int auxiliar = numerosdigitados[i];
                numerosdigitados[i] = numerosdigitados[j];
                numerosdigitados[j] = auxiliar;
            }
        }
    }

    // 3. Imprimindo o resultado final (DEPOIS que a ordenação terminou)
    Console.WriteLine("\nOs números em ordem crescente são:");
    foreach (int numero in numerosdigitados)
    {
        Console.WriteLine(numero);
    }


# Exercício de Numero 2 (Exibir o maior nome digitado)

Agora algo mais simples, vamos desenvolver um aplicativo onde são coletados 7 nomes/palavras, e exibirmos apenas a maior delas

Codigo:

    // variavel que coleta os nome
    string [] nomes = new string[8];
    
    // logica de digitar os nomes
    for (int i = 0; i < nomes.Length; i++)
    {
        Console.Write("Digite o nome da pessoa " + (i + 1) + ": ");
        nomes[i] = Console.ReadLine();
    }
    // posição do maior nome(inicia com 0)
    int posicaoMaiorNome = 0;
    
    // percorre o array de nomes a partir do segundo elemento
    for (int i = 1; i < nomes.Length; i++)
    {
        // compara o tamanho do nome atual com o maior nome encontrado 
        if (nomes[i]./*qual comando usamos para pegar o tamanho do vetor?*/ > nomes[posicaoMaiorNome].Length)
        {
            posicaoMaiorNome = /*posição do maior numero deve ser igual a qual?*/; // atualiza a posição do maior nome
        }
    }
    
    // exibe o maior nome encontrado
    Console.WriteLine("O maior nome é: " + nomes[/*qual variavel devemos colocar aqui?*/]);

# Exercício 3 ( Verificador de CPF)

## Atenção! Leia com bastante atenção o enunciado, pois ele vai ser importante para resolver o exercício

O CPF brasileiro é um documento muito importante em muitos processos, já que ele é o unico documento onde é impossivel possuir mais de uma pessoa com mesmo nome.

Mas o CPF não é uma sequência de números aleatórios.

Regras do CPF:

1° - Ele é composto por um total de 11 digitos, sendo os 8 primeiros aleatórios e o 9° dependendo da unidade federativa (estado) em que a pessoa nasceu.

2° - o décimo digito é o primeiro digito verificador, ele é definido pelo seguinte calculo:

pegamos o primeiro numero e multiplicamos por 10, o segundo por 9, o terceiro por 8 e assim por diante... após isso, somamos todos esses números e dividirmos por 11, se o resto da divisão for menor do que 2, o primeiro digito verificador é "0", caso o contrario, fazemos 11 - resto dessa divisão, o resultado é o primeiro digito verificador

Exemplo: 123.456.789

1 * 10 = 10

2 * 9 = 18

3 * 8 = 24

4 * 7 = 28

5 * 6 = 30

6 * 5 = 30

7 * 4 = 28

8 * 3 = 24

9 * 2 = 18

total = 210

210 % 11 = 1

Primeiro digito verificador = 0

3° - O décimo primeiro digito é o segundo digito verificador. O cálculo é quase igual, mas agora usamos os 10 primeiros dígitos (os 9 da base + o primeiro digito verificador que acabamos de achar) e os pesos começam em 11:

Exemplo: Usando 123.456.789 e o DV1 (0) que achamos -> (123.456.789-0)

1 * 11 = 11

2 * 10 = 20

3 * 9 = 27

4 * 8 = 32

5 * 7 = 35

6 * 6 = 36

7 * 5 = 35

8 * 4 = 32

9 * 3 = 27

0 * 2 = 0

total = 255

255 % 11 = 2

O resto (2) não é menor que 2, então fazemos: 11 - 2 = 9

Segundo digito verificador = 9

Portanto, o CPF completo e válido seria: 123.456.789-09

4° - Regra Especial: CPFs com todos os dígitos iguais (como 111.111.111-11, 222.222.222-22, etc.) são considerados INVÁLIDOS, mesmo que por acaso passem pela regra de cálculo.

Conclusão:

Para um CPF ser considerado VÁLIDO:

Ele não pode ter todos os dígitos iguais.

O primeiro dígito verificador calculado (DV1) deve ser igual ao 10º dígito do CPF.

O segundo dígito verificador calculado (DV2) deve ser igual ao 11º dígito do CPF.


Código:

    using System;

    public class program
    {
    // Método Main para execução do programa
    public static void Main(string[] args)
    {
        // pedir para o usuário digitar um CPF
         Console.WriteLine("Digite um CPF para validar (formato: xxx.xxx.xxx-xx):");
         // Ler o CPF 
         string cpfInput = Console.ReadLine();
        
        // variav0el bool para armazenar o resultado da validação
        bool isValid = ValidarCPF(cpfInput);
          
        // O que fazer com o resultado
        if (/*O que deve ser verdadeiro?*/ == true)
        {
            //cpf válido
            Console.WriteLine("CPF válido.");
        }
        // caso o contrário
        else
        {
            //cpf inválido
            Console.WriteLine("CPF inválido.");
        }
    }

    // Função principal que valida o CPF
    public static bool ValidarCPF(string cpf)
    {
        // Comandos para tirar os caracteres especiais para facilitar a validação
        cpf = cpf.Replace(".", "").Replace("-", "");

        // Qual deve ser o tamanho do CPF após remover os caracteres especiais? 
        if (cpf.Length != /*Quanto caracteres um CPF tem?*/)
        {
            return false;
        }

        // Verificação de CPFs inválidos conhecidos (todos os dígitos iguais)
        bool todosDigitosIguais = true;
        // Loop para verificar se todos os dígitos são iguais
        for (int i = 1; i < cpf.Length; i++)
        {
            // se o dígito atual for diferente do primeiro dígito
            if (cpf[/**/] != cpf[0])
            {
                // todos os dígitos não são iguais
                todosDigitosIguais = false;
                break; // Se achar um diferente, para o loop
            }
        }
        // Se todos os dígitos forem iguais, o CPF é inválido
        if (todosDigitosIguais)
        {
            return false;
        }

        // Converte a string do CPF em um vetor de números inteiros
        int[] digitosCpf = new int[11];
        for (int i = 0; i < 11; i++)
        {
             // comando para converter cada caractere em número inteiro
            digitosCpf[i] = int.Parse(cpf[i].ToString());
        }

        // Cálculo do PRIMEIRO dígito verificador (DV)

        // Vetor (array) com os pesos para o primeiro DV
        int[] pesosDV1 = { /* qual deve ser o array do primeiro digito verificador?*/};

        // Variável para armazenar a soma dos produtos
        int soma = 0;

        // Multiplica os 9 primeiros dígitos do CPF pelos pesos
        for (int i = 0; i < 9; i++)
        {
            soma += digitosCpf[i] * pesosDV1[i];
        }

        // segue o cálculo do resto da divisão da soma por 11
        int resto = soma % 11;

        // Cálculo do DV1 baseado no resto
        int dv1Calculado = (resto < 2) ? 0 : 11 - resto;

        //Verificação do PRIMEIRO DV
        // Compara o DV calculado com o DV informado (décimo dígito)
        if (dv1Calculado != digitosCpf[9])
        {
            return false;
        }

        // Cálculo do SEGUNDO dígito verificador (DV)

        // Vetor (array) com os pesos para o segundo DV
        int[] pesosDV2 = {/* qual deve ser o array do segundo digito verificador?*/};

        soma = 0; // Reseta a soma

        // Multiplica os 10 primeiros dígitos (incluindo o DV1) pelos pesos
        for (int i = 0; i < 10; i++)
        {
            soma += digitosCpf[/*qual valor deve estar aqui?*/] * pesosDV2[/*qual valor deve estar aqui?*/];
        }

        resto = soma % 11;
        int dv2Calculado = (resto < 2) ? 0 : 11 - resto;

        // 8Verificação do SEGUNDO DV
        // Compara o DV calculado com o DV informado (décimo primeiro dígito)
        if (dv2Calculado != digitosCpf[10])
        {
            return false;
        }

        // Se passou por todas as verificações, o CPF é válido
        return true;
    }
    }
