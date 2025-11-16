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

# Exercícip 3 ()
