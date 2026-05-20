# Hands-On-5
Hands On 5 

Atividades da Rafaela 

Atividade 1) 

import java.util.ArrayList;

public class ListaCompras {

    public static void main(String[] args) {

        ArrayList<String> produtos = new ArrayList<>();

        produtos.add("Monster");
        produtos.add("Monster Branco");
        produtos.add("RedBull");
        produtos.add("RedBull Tropical");
        produtos.add("Monster Mango Loco");

        System.out.println("Lista de compras:");

        for (String produto : produtos) {

            System.out.println(produto);
        }

        System.out.println("\nQuantidade de produtos: " + produtos.size());
    }
}

Atividade 2 )

import java.util.ArrayList;

public class NotasTurma {

    public static void main(String[] args) {

        ArrayList<Double> notas = new ArrayList<>();

        notas.add(8.0);
        notas.add(7.5);
        notas.add(6.0);
        notas.add(9.0);

        double soma = 0;

        for (double nota : notas) {

            soma = soma + nota;
        }

        double media = soma / notas.size();

        System.out.println("Media da turma: " + media);

        if (media >= 7) {

            System.out.println("Turma aprovada!");

        } else {

            System.out.println("Turma reprovada!");
        }
    }
}

Atividade 3 ) 

import java.util.HashSet;

public class AlunosPresentes {

    public static void main(String[] args) {

        HashSet<String> alunos = new HashSet<>();

        alunos.add("Renganeschi");
        alunos.add("Mariana");
        alunos.add("Ray");
        alunos.add("Ana Carolina");
        alunos.add("Cristiano Ronaldo");

        System.out.println("Lista final sem repeticao:");

        for (String nome : alunos) {

            System.out.println(nome);
        }

        System.out.println("\nQuantidade de alunos: " + alunos.size());
    }
}

Atividade 4 ) 

import java.util.HashMap;

public class CadastroAlunos {

    public static void main(String[] args) {

        HashMap<Integer, String> alunos = new HashMap<>();

        alunos.put(1, "Renganeschi");
        alunos.put(2, "Ana Carolina");
        alunos.put(3, "Ray");

        System.out.println("Aluno da matricula 2:");
        System.out.println(alunos.get(2));

        alunos.remove(3);

        System.out.println("\nLista de alunos:");

        for (Integer matricula : alunos.keySet()) {

            System.out.println(
                "Matricula: " + matricula +
                " Nome: " + alunos.get(matricula)
            );
        }
    }
}

Atividade 5 )

import java.util.LinkedList;
import java.util.Queue;

public class FilaClientes {

    public static void main(String[] args) {

        Queue<String> fila = new LinkedList<>();

        fila.add("Renganeschi");
        fila.add("Rafaela");
        fila.add("Ray");
        fila.add("Ana Carolina");
        fila.add("Severino");

        System.out.println("Proximo cliente:");
        System.out.println(fila.peek());

        fila.poll();
        fila.poll();

        System.out.println("\nFila atualizada:");

        for (String cliente : fila) {

            System.out.println(cliente);
        }
    }
}

Atividade 6 ) 

public class Livro {

    int codigo;
    String titulo;
    String autor;
    boolean disponivel;

    public Livro(int codigo, String titulo, String autor) {

        this.codigo = codigo;
        this.titulo = titulo;
        this.autor = autor;

        this.disponivel = true;
    }
}

import java.util.ArrayList;
import java.util.Scanner;

public class Biblioteca {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        ArrayList<Livro> livros = new ArrayList<>();

        int opcao;

        do {

            System.out.println("\n1-Cadastrar");
            System.out.println("2-Listar");
            System.out.println("3-Emprestar");
            System.out.println("4-Devolver");
            System.out.println("0-Sair");

            opcao = sc.nextInt();

            if (opcao == 1) {

                System.out.print("Codigo: ");
                int codigo = sc.nextInt();

                sc.nextLine();

                System.out.print("Titulo: ");
                String titulo = sc.nextLine();

                livros.add(new Livro(codigo, titulo));

            }

            else if (opcao == 2) {

                for (Livro l : livros) {

                    System.out.println(l.codigo + " - " + l.titulo);

                    if (l.disponivel) {

                        System.out.println("Disponivel");

                    } else {

                        System.out.println("Emprestado");
                    }
                }
            }

            else if (opcao == 3) {

                System.out.print("Codigo do livro: ");
                int codigo = sc.nextInt();

                for (Livro l : livros) {

                    if (l.codigo == codigo) {

                        l.disponivel = false;
                    }
                }
            }

            else if (opcao == 4) {

                System.out.print("Codigo do livro: ");
                int codigo = sc.nextInt();

                for (Livro l : livros) {

                    if (l.codigo == codigo) {

                        l.disponivel = true;
                    }
                }
            }

        } while (opcao != 0);
    }
}

Atividade 7 ) 

public class Pedido {

    int numero;
    String nome;
    double valor;

    public Pedido(int n, String no, double v) {

        numero = n;
        nome = no;
        valor = v;
    }
}

import java.util.ArrayList;
import java.util.Scanner;

public class Lanchonete {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        ArrayList<Pedido> pedidos = new ArrayList<>();
        
        System.out.print("Numero do pedido: ");
        int numero = sc.nextInt();

        sc.nextLine();

        System.out.print("Nome do cliente: ");
        String nome = sc.nextLine();

        System.out.print("Valor: ");
        double valor = sc.nextDouble();

        Pedido p = new Pedido(numero, nome, valor);

        pedidos.add(p);
        
        System.out.println("\nPEDIDOS:");

        for (Pedido pedido : pedidos) {
            System.out.println(pedido.numero);
            System.out.println(pedido.nome);
            System.out.println(pedido.valor);
        }
        double total = 0;

        for (Pedido pedido : pedidos) {

            total = total + pedido.valor;
        }
        System.out.println("\nTotal: " + total);
    }
}
