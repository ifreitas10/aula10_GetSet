# aula10_GetSet

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

------------------------------------------------------------------------------------------
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
