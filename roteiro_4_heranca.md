# Roteiro 4 - POO I
## Herança, Composição e Interfaces

Respostas dos exercícios do roteiro.

---

## Exercício 01 — Herança: Veículos

```csharp
using System;

class Veiculo
{
    public string Marca;
    public string Modelo;
    public int NumeroDeRodas;

    public void ExibirDados()
    {
        Console.WriteLine("Marca: " + Marca);
        Console.WriteLine("Modelo: " + Modelo);
        Console.WriteLine("Número de rodas: " + NumeroDeRodas);
    }
}

class Carro : Veiculo
{
    public int NumeroDePortas;
}

class Moto : Veiculo
{
    public bool PossuiBagageiro;
}

class Program
{
    static void Main()
    {
        Carro carro = new Carro();

        carro.Marca = "Toyota";
        carro.Modelo = "Corolla";
        carro.NumeroDeRodas = 4;
        carro.NumeroDePortas = 4;

        carro.ExibirDados();
        Console.WriteLine("Número de portas: " + carro.NumeroDePortas);

        Console.WriteLine();

        Moto moto = new Moto();

        moto.Marca = "Honda";
        moto.Modelo = "CG 160";
        moto.NumeroDeRodas = 2;
        moto.PossuiBagageiro = true;

        moto.ExibirDados();
        Console.WriteLine("Possui bagageiro: " + moto.PossuiBagageiro);
    }
}
```

---

## Exercício 02 — Composição

```csharp
using System;

class Pessoa
{
    public string Nome;
}

class Casa
{
    private Pessoa pessoa;

    public void ExibirMorador()
    {
        Console.WriteLine("Morador: " + pessoa.Nome);
    }

    public void ColocarPessoa(Pessoa pessoa)
    {
        this.pessoa = pessoa;
    }
}

class Program
{
    static void Main()
    {
        Pessoa pessoa = new Pessoa();

        pessoa.Nome = "Carlos";

        Casa casa = new Casa();

        casa.ColocarPessoa(pessoa);

        casa.ExibirMorador();
    }
}
```

---

## Exercício 03 — Interface

```csharp
using System;

interface IVeiculo
{
    void Mover();
}

class Carro : IVeiculo
{
    public void Mover()
    {
        Console.WriteLine("O carro está se movendo");
    }
}

class Bicicleta : IVeiculo
{
    public void Mover()
    {
        Console.WriteLine("A bicicleta está se movendo");
    }
}

class Program
{
    static void Main()
    {
        Carro carro = new Carro();
        Bicicleta bicicleta = new Bicicleta();

        carro.Mover();
        bicicleta.Mover();
    }
}
```

---

## Exercício 04 — Uma classe, várias interfaces

```csharp
using System;

interface IVoar
{
    void Voar();
}

interface INadar
{
    void Nadar();
}

class Pato : IVoar, INadar
{
    public void Voar()
    {
        Console.WriteLine("O pato está voando");
    }

    public void Nadar()
    {
        Console.WriteLine("O pato está nadando");
    }
}

class Aguia : IVoar
{
    public void Voar()
    {
        Console.WriteLine("A águia está voando");
    }
}

class Peixe : INadar
{
    public void Nadar()
    {
        Console.WriteLine("O peixe está nadando");
    }
}

class Program
{
    static void Main()
    {
        Pato pato = new Pato();
        pato.Voar();
        pato.Nadar();

        Aguia aguia = new Aguia();
        aguia.Voar();

        Peixe peixe = new Peixe();
        peixe.Nadar();
    }
}
```
