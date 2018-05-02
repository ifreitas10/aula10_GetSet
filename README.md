# aula10_GetSet
//DESAFIO 1
public class Cadastro {
    private int senha;
    private int numero1;
    private int numero2;

    public int getSenha(){
        return senha;
    }

    public void setSenha(int senha){
        this.senha = senha;
    }

    public int getNumero1(){
        return numero1;
    }

    public void setNumero1(int numero1){
        this.numero1 = numero1;
    }

    public int getNumero2(){
        return numero2;
    }

    public void setNumero2(int numero2){
        this.numero2 = numero2;
    }
}

------------------------------------------------------------------------------------------------------------------
//DESAFIO 1
import javax.swing.*;
public class Controlador {
    int soma;

    public static int somar(int numero1, int numero2){
        int soma = numero1+numero2;
        return soma;
    }

    public static void main(String[] args){
        Cadastro usuario = new Cadastro();
        usuario.setSenha(Integer.parseInt(JOptionPane.showInputDialog("Digite a senha")));
        usuario.setNumero1(Integer.parseInt(JOptionPane.showInputDialog("Digite um número")));
        usuario.setNumero2(Integer.parseInt(JOptionPane.showInputDialog("Digite um número")));

        int senha = usuario.getSenha();
        int numero1 = usuario.getNumero1();
        int numero2 = usuario.getNumero2();
        int soma;
        int confirmaSenha = Integer.parseInt(JOptionPane.showInputDialog("Digite a senha novamente"));

        if (confirmaSenha == senha){
            soma = somar(numero1,numero2);
            JOptionPane.showMessageDialog(null,"A soma dos valores recebidos: "+soma);
        }else{
            JOptionPane.showMessageDialog(null,"Senha incorreta");
        }
    }
}
------------------------------------------------------------------------------------------------------------------
//Desafio 2

public class Cadastro {
    private Double valorVeiculo;
    private int anoVeiculo;
    private int totalVeiculo;
    private int totalVeiculo2000;

    public Double getValorVeiculo(){
        return valorVeiculo;
    }

    public void setValorVeiculo(Double valorVeiculo){
        this.valorVeiculo = valorVeiculo;
    }

    public int getAnoVeiculo(){
        return anoVeiculo;
    }

    public void setAnoVeiculo(int anoVeiculo){
        this.anoVeiculo = anoVeiculo;
    }

    public int getTotalVeiculo(){
        return totalVeiculo;
    }

    public void incrementaTotalVeiculo(){
        this.totalVeiculo += 1;
    }

    public int getTotalVeiculo2000(){
        return totalVeiculo2000;
    }

    public void incrementaTotalVeiculo2000(){
        this.totalVeiculo2000 += 1;
    }
}
------------------------------------------------------------------------------------------------------------------
//Desafio 2
public class Controlador {
   public static void receberDadosVeiculo(Cadastro carro){
        int anoVeiculo;
        Double valorVeiculo;
        Double valorVeiculoComDesconto;
        Double valorTotalVeiculoComDesconto;

        DecimalFormat formatador = new DecimalFormat("###,###,##0.00");

        carro.setValorVeiculo(Double.parseDouble(JOptionPane.showInputDialog("Digite o valor do veículo")));
        carro.setAnoVeiculo(Integer.parseInt(JOptionPane.showInputDialog("Digite o ano do veículo")));

        valorVeiculo = carro.getValorVeiculo();
        anoVeiculo = carro.getAnoVeiculo();


        if (anoVeiculo <= 2000){
            valorVeiculoComDesconto = (valorVeiculo * 0.12);
            valorTotalVeiculoComDesconto = valorVeiculo - valorVeiculoComDesconto;
            carro.incrementaTotalVeiculo();
            carro.incrementaTotalVeiculo2000();
        }else{
            valorVeiculoComDesconto = (valorVeiculo * 0.07);
            valorTotalVeiculoComDesconto = valorVeiculo - valorVeiculoComDesconto;
            carro.incrementaTotalVeiculo();
        }

        JOptionPane.showMessageDialog(null,"Valor do veiculo: "+formatador.format(valorVeiculo)+"R$"+" com desconto de "+formatador.format(valorVeiculoComDesconto)+"R$\nValor do veículo com desconto: "+formatador.format(valorTotalVeiculoComDesconto)+"R$");
        desejaContinuar(carro);
    }

    public static void desejaContinuar(Cadastro carro){
        String desejaContinuar = JOptionPane.showInputDialog("Deseja continuar?");

        if (desejaContinuar.equals("s")){
            receberDadosVeiculo(carro);
        }else{
            JOptionPane.showMessageDialog(null,"Quantidade de carros: "+carro.getTotalVeiculo()+"\nQuantidade de carros com ano até 2000: \n"+carro.getTotalVeiculo2000());
            //JOptionPane.showMessageDialog(null,"Quantidade de carros com ano até 2000: " +carro.getTotalVeiculo2000());
            //JOptionPane.showMessageDialog(null,"SAIU");
        }
    }

    public static void main(String[] args){
        Cadastro carro = new Cadastro();
        receberDadosVeiculo(carro);
    }
}
