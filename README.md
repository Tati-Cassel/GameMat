# GameMat
Aplicação de console -> Jogo que gera fórmulas matemáticas com dificuldades em 4 níveis e com um placar de pontos.

#include <stdio.h>
#include <stdlib.h>

int somar(int v1, int v2)
{
    int resultado = 0;

    resultado = v1 + v2;

    return resultado;
}

int subtrair(int v1, int v2)
{
    int resultado = 0;

    if (v2 > v1)
    {
        resultado = v2 - v1;
    }
    else
    {
        resultado = v1 - v2;
    }

    return resultado;
}

int multiplicar(int v1, int v2)
{
    int resultado = 0;

    resultado = v1 * v2;

    return resultado;
}

int main()
{
    int intFinaliza = 2;

    while (intFinaliza == 2)
    {
        int intNivelDif    = 0;
        int intAltNivelDif = 0;
        int intZeraPlacar  = 2;
        int intNumExecut   = 0;
        int intValor1      = 0;
        int intValor2      = 0;
        int intOperacao    = 0;
        int intValorInf    = 0;
        int intPlacar      = 0;

        do
        {
            intValor1 = 0;
            intValor2 = 0;
            intOperacao = 0;

            fprintf(stdout, "-----------------------------------------------------------\n");
            fprintf(stdout, "-------------------------/GameMat/-------------------------\n");
            fprintf(stdout, "-----------------------------------------------------------\n\n\n");

            if (intNumExecut == 0)
            {
                fprintf(stdout,"Escolha o Nivel de dificuldade:\n\n");
                fprintf(stdout,"( 1 ) Nivel 1\n");
                fprintf(stdout,"( 2 ) Nivel 2\n");
                fprintf(stdout,"( 3 ) Nivel 3\n");
                fprintf(stdout,"( 4 ) Nivel 4\n\n");
                fprintf(stdout,"Nivel escolhido -> ");
                scanf_s("%d", &intNivelDif);
                fflush(stdin);

                intNumExecut = 1;
            }

            intOperacao = rand() % 3;

            switch (intNivelDif)
            {
            case 1:
            {
                intValor1 = rand() % 11; //0 a 10
                intValor2 = rand() % 11;
                break;
            }
            case 2:
            {
                intValor1 = rand() % 101;
                intValor2 = rand() % 101;
                break;
            }
            case 3:
            {
                intValor1 = rand() % 1001;
                intValor2 = rand() % 1001;
                break;
            }
            case 4:
            {
                intValor1 = rand() % 10001;
                intValor2 = rand() % 10001;
                break;
            }
            default:
            {
                intValor1 = rand() % 5;
                intValor2 = rand() % 1000;
                break;
            }
            }

            switch (intOperacao)
            {
                case 0:
                {
                    int soma = 0;

                    soma = somar(intValor1, intValor2);

                    fprintf(stdout, "\nResolva a operacao: \n");
                    fprintf(stdout, "--------------------\n");
                    fprintf(stdout, "%d + %d = ?\n", intValor1, intValor2);
                    fprintf(stdout, "--------------------\n\n");
                    fprintf(stdout, "->");
                    scanf_s("%d", &intValorInf);
                    fflush(stdin);

                    if (soma == intValorInf)
                    {
                        intPlacar = intPlacar + 1;

                        fprintf(stdout, "\nVoce acertou!\n");
                        fprintf(stdout, "% d + % d = %d \n", intValor1, intValor2, soma);
                        fprintf(stdout, "\n-----> Placar: %d  - [Dificuldade nivel: %d] <-----\n", intPlacar, intNivelDif);
                    }
                    else
                    {
                        fprintf(stdout, "\nVoce errou!\n");
                        fprintf(stdout, " % d + % d = %d \n", intValor1, intValor2, soma);
                        fprintf(stdout, "\n-----> Placar: %d  - [Dificuldade nivel: %d] <-----\n", intPlacar, intNivelDif);
                    }

                    break;
                }
                case 1:
                {
                    int subtrai = 0;

                    subtrai = subtrair(intValor1, intValor2);

                    fprintf(stdout, "\nResolva a operacao: \n");
                    fprintf(stdout, "--------------------\n");
                    fprintf(stdout, "%d - %d = ?\n", intValor1, intValor2);
                    fprintf(stdout, "--------------------\n\n");
                    fprintf(stdout, "->");
                    scanf_s("%d", &intValorInf);
                    fflush(stdin);

                    if (subtrai == intValorInf)
                    {
                        intPlacar = intPlacar + 1;

                        fprintf(stdout, "\nVoce acertou!\n");
                        fprintf(stdout, "% d - % d = %d \n", intValor1, intValor2, subtrai);
                        fprintf(stdout, "\n-----> Placar: %d  - [Dificuldade nivel: %d] <-----\n", intPlacar, intNivelDif);
                    }
                    else
                    {
                        fprintf(stdout, "\nVoce errou!\n");
                        fprintf(stdout, " % d - % d = %d \n", intValor1, intValor2, subtrai);
                        fprintf(stdout, "\n-----> Placar: %d  - [Dificuldade nivel: %d] <-----\n", intPlacar, intNivelDif);
                    }
                    break;
                }
                case 2:
                {
                    int multiplica = 0;

                    multiplica = multiplicar(intValor1, intValor2);

                    fprintf(stdout,"\nResolva a operacao: \n");
                    fprintf(stdout,"--------------------\n");
                    fprintf(stdout,"%d x %d = ?\n", intValor1, intValor2);
                    fprintf(stdout,"--------------------\n\n");
                    fprintf(stdout,"->");
                    scanf_s("%d", &intValorInf);
                    fflush(stdin);

                    if (multiplica == intValorInf)
                    {
                        intPlacar = intPlacar + 1;

                        fprintf(stdout, "\nVoce acertou!\n");
                        fprintf(stdout, "% d x % d = %d \n", intValor1, intValor2, multiplica);
                        fprintf(stdout, "\n-----> Placar: %d  - [Dificuldade nivel: %d] <-----\n", intPlacar, intNivelDif);
                    }
                    else
                    {
                        fprintf(stdout, "\nVoce errou!\n");
                        fprintf(stdout, " % d x % d = %d \n", intValor1, intValor2, multiplica);
                        fprintf(stdout, "\n-----> Placar: %d  - [Dificuldade nivel: %d] <-----\n", intPlacar, intNivelDif);
                    }
                    break;
                }
            }

            fprintf(stdout, "\n\nDeseja zerar o placar? (1-Sim)(2-Nao) -> ");
            scanf_s("%d", &intZeraPlacar);
            fflush(stdin);

            fprintf(stdout, "\n\nDeseja mudar o nivel? [1-2-3-4] [999 - Nao]-> ");
            scanf_s("%d", &intAltNivelDif);
            fflush(stdin);

            if (intAltNivelDif != 999)
            {
                intNivelDif = intAltNivelDif;
            }

            system("cls");

        } while (intZeraPlacar == 2);

        fprintf(stdout, "Deseja encerrar a aplicacao? (1-Sim)(2-Nao) -> ");
        scanf_s("%d", &intFinaliza);
        fflush(stdin);

        system("cls");
    }

    return 0;
}
