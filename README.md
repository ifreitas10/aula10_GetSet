# aula10_GetSet

public class Cadastro {
    private int senha;
    private int numero1;
    private int numero2;
    private int soma;

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
public class Controlador {
    int soma;

    public static void main(String[] args){


    Cadastro avaliar = new Cadastro();
    avaliar.setSenha(Integer.parseInt(JOptionPane.showInputDialog("Digite a senha")));
    avaliar.setNumero1(Integer.parseInt(JOptionPane.showInputDialog("Digite um número")));
    avaliar.setNumero2(Integer.parseInt(JOptionPane.showInputDialog("Digite um número")));
    //System.out.println(avaliar.getSenha());
    // System.out.println(avaliar.getNumero1());

    int senha = avaliar.getSenha();
    int numero1 = avaliar.getNumero1();
    int numero2 = avaliar.getNumero2();
    int somar;
    int confirmaSenha = Integer.parseInt(JOptionPane.showInputDialog("Digite a senha novamente"));

        if (confirmaSenha == senha){
            somar = numero1+numero2;
            JOptionPane.showMessageDialog(null,somar);
        }else{
            JOptionPane.showMessageDialog(null,"Senha incorreta");
        }
    }
}
