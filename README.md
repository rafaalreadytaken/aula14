# aula14

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aula_14___Exercicio
{
    class Program
    {
        static void Main(string[] args)
        {
            double valorAtualizado;

            produtos produto = new produtos();
            Console.WriteLine("Entre os dados do Produto:");
            Console.Write("Nome: ");
            produto.Nome = Console.ReadLine();
            Console.Write("Preço: ");
            produto.Preco = Convert.ToDouble(Console.ReadLine());
            Console.Write("Quantidade no estoque: ");
            produto.Quantidade = int.Parse(Console.ReadLine());

            Console.WriteLine("Dados do protudo:" + produto.Nome +", " + "$" + produto.Preco + ", " + produto.Quantidade + " Unidades" + ", " + "Total : $" + produto.ValorTotalEmEstoque());

            Console.Write("Digite quantos produtos serão adicionados: ");
            produto.Adicionados = int.Parse(Console.ReadLine());
            Console.WriteLine("Dados Atualizado: " + produto.Nome + ", " + "$" + produto.Preco + ", " + produto.AdicionarProdutos() + " Unidades" +"Total : $" + (produto.AdicionarProdutos() * produto.Preco) );


            Console.WriteLine("Digite quantos produtos serão retirados: ");
            produto.Removidos =int.Parse(Console.ReadLine());
            Console.Write("Dados Atualizado: " + produto.Nome + ", " + "$" + produto.Preco + ", " + produto.RemoverProdutos() + " Unidades" + "Total : $" + (produto.RemoverProdutos() * produto.Preco));
        }
    }
}


------------------------------------------------------------------------------

//classe

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aula_14___Exercicio
{
    class produtos
    {
        public string Nome;
        public double Preco;
        public int Quantidade;
        public int Adicionados;
        public int Removidos;
      public double   ValorTotalEmEstoque()
        {
            double totalestoque;
            totalestoque = Quantidade * Preco;
            return totalestoque;
        }

        public int AdicionarProdutos()
        {
            int totalAdicionados;
            
            totalAdicionados = Quantidade + Adicionados;
           return totalAdicionados;
        }

        public  int RemoverProdutos()
        {
            int totalRemovido;
            totalRemovido = (AdicionarProdutos() - Removidos);
           return totalRemovido;
        }
    }
   

}

