// LIST NÃO ACEITA TIPOS PRIMITIVOS, ACEITA APENAS WRAPPER CLASS.

// O TIPO .STREAM É UM TIPO ESPECIAL DO VAJA8 EM DIANTE QUE ACEITA OPERAÇÕES COM EXPRESSÕES LAMBDA

package application;

import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class Program {

	public static void main(String[] args) {

		List<String> list = new ArrayList<>();

		list.add("Maria");
		list.add("Alex");
		list.add("Bob");
		list.add("Anna");
		list.add(2, "Marco"); // adicionar o Marco na posição DOIS

		System.out.println(list.size()); // para ver o tamanho da lista
		
		for (String x : list) {
			System.out.println(x);
		}
		System.out.println("------------------------------------------------------------------------------------------");
		
		list.remove("Anna"); // a lista tem uma operação que é capaz de remover um dado apartir da comparação do valor dele com outra		
		
		list.remove(1); // remove quem está na posição UM
		
		list.removeIf(x -> x.charAt(0) == 'M'); // definido pela função lambida, essa função lambda em particular, ela se chama predicado, pq? ela é uma função que vai me retornar em verdadeiro ou falso, ela remove todos que começam com a letra 'M'
		
		for (String x : list) {
			System.out.println(x);
		}
		System.out.println("------------------------------------------------------------------------------------------");
		
		System.out.println("Index of Bob: " + list.indexOf("Bob")); // vamo supor que eu quero encontrar a posição de um elemento
		System.out.println("Index of Marco: " + list.indexOf("Marco")); // quando o indexOf não encontra o elemento, ele retorna -1
		
		System.out.println("------------------------------------------------------------------------------------------");
		
		list.add("Maria");
		list.add("Alex");
		list.add("Bob");
		list.add("Anna");
		list.add(2, "Marco");
		
		for (String x : list) {
			System.out.println(x);
		}
		System.out.println("------------------------------------------------------------------------------------------");
		
		List<String> result = list.stream().filter(x -> x.charAt(0) == 'A').collect(Collectors.toList());
		/*
		 *  vamos supor que eu quero filtra minha lista com todo mundo que começa com 'A'.
		 *  ele pega minha LISTA (list), que é a original, filtra nessa lista somente aqueles
		 *  elementos que começa com 'A', e devolve pra mim uma nova lista (result) somente com esses elementos 	
		 */
		for (String x : result) {
			System.out.println(x);
		}
		System.out.println("------------------------------------------------------------------------------------------");
		
		String name = list.stream().filter(x -> x.charAt(0) == 'A').findFirst().orElse(null);
		String name2 = list.stream().filter(x -> x.charAt(0) == 'J').findFirst().orElse(null);
		
		/*
		 *  vamos aprender como que a gente faz para encontrar um elemento da lista que atenda um certo
		 *  predicado , como assim.
		 *  vamos supor que eu quero encontrar o primeiro elemento que comece com a letra 'A', que no caso 
		 *  é o Alex, como é que eu faço isso? 
		 */
		System.out.println(name);
		System.out.println(name2); // se ele não encontrar, ele vai me voltar NULO.
		
	}

}
