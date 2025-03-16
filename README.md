# Desafio-n-vel-mestre-Compara-es-Avan-adas-com-Atributos-M-ltiplos

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(){

    char pais1 [50] = "Inglaterra", pais2 [50] = "Grécia"; 
    float Populacao1 = 10.423000, Populacao2 = 56.700000, resultadoPopulacao;
    float area1 = 132.000, area2 = 130.395, resultadoArea; 
    float pib1 = 312.000000, pib2 = 209.860000 , resultadopPib;
    int NumeroPontosTuristicos1 = 8, NumeroPontosTuristicos2 =7, resultadoNumTuristico;
    float densidadeDemogratica1 = 433, densidaDemografica2 = 89, resultadoDemografico;
    int escolhaMenu, comparacao1, comparacao2, resultado1, resultado2, resultadoFinal;
   int atrib1 =0 , atrib2 =0; // atributos para efetuar o recebimento do valor caso um ganhe e para efetuar o desempate
    
    printf("####### JOGO SUPER TRUNFO DE PAÍSES #####\n");
    printf("\n");
    printf(" O jogo se dará entre países \n");
    printf(" %s  x  %s  \n", pais1, pais2);
    printf(" Selecione as Opções \n");

    printf(" 1. Regras do jogo \n");
    printf(" 2. Começar o Jogo \n");
    printf(" 3. Sair do Jogo \n");
    printf(" Escolha uma das ACIMA: ");
    scanf ("%d", &escolhaMenu);
    
    switch (escolhaMenu){
    case 1:  /// regras dos jogo
            printf(" As regras são as seguintes\n");
            printf(" 1º Regra: Os numeros de comparações são limitados \n");
            printf(" 2º Regra: Escolha entre as 5 opções de comparação, demais opções não funcionarão \n");
            printf(" Ganha o jogo tem tiver o maior valor da comparação selecionada \n");
            
    break; // inico de jogo
    case 2: printf(" \n");
            printf(" #### VAMOS COMEÇAR O JOGO ######\n");
            printf(" \n");
            printf(" Vamos lá, escolha entre as opções de comparação para ver qual dos Países é melhor \n");
            printf(" %s  x  %s  \n", pais1, pais2);
            printf(" \n");

            printf ("1. Maior População \n");
            printf ("2. Maior area \n");
            printf ("3. Maior PIB \n");
            printf ("4. Pontos turisticos \n");
            printf ("5. Densidade Demográfica\n ");
            printf(" \n");

            printf (" Escolha a Primeira opção Para comparar : ");
            scanf("%d", &comparacao1);
            printf(" \n");

            printf (" Escolha a Segunda Opção de Comparação : ");
            scanf("%d",&comparacao2);
            printf(" \n");

            // aqui é para ele não sair e não colocar duas opções iguas
            if (comparacao1 == comparacao2){  
                printf(" Você não pode selecionar a mesma opção duas vezes");
                break;
            }
            switch (comparacao1){  // esse primeiro switch é para a primerira escolha de comparação
            case 1: 
                    printf(" \n");
                    printf(" Você escolheu comparar qual tem a maior população! \n");
                    printf(" A população de  %s tem um total de = %f  e %s tem um total de = %f \n", pais1, Populacao1, pais2, Populacao2);                  
                    resultado1 = Populacao1 > Populacao2 ? 1 :0;                
                   
                    if(resultado1 == 1){
                        printf(" %s Venceu ! Com população de %f \n", pais1, Populacao1);
                           atrib1 = 1 ; 
                    }else{
                        printf(" %s Venceu ! Com população de %f, e    \n", pais2, Populacao2);
                        atrib2 = !resultado1;  // ponto de exclamação nega o 0 tranformando em 1 para no final efetuar o desempate caso haja
                    }
                break;
            case 2: 
                    printf(" \n");
                    printf(" Você escolheu comparar a AREA \n");
                    printf(" A Area de  %s tem um total de = %f  e %s tem um total de = %f\n", pais1, area1, pais2, area2);                  
                    resultado1 = area1 > area2 ? 1 : 0;

                    if(resultado1 == 1){
                        printf(" %s venceu ! Com area de %f \n", pais1, area1);
                        atrib1 = 1;
                    }else{
                        printf(" %s venceu ! Com area de %f, e    \n", pais2, area2);
                        atrib2 = !resultado1;
                    }
                break;    
            case 3: 
                    printf(" \n");
                    printf(" Você escolheu comparar o PIB \n");
                    printf(" O Pib de  %s tem um total de = %f  e %s tem um total de = %f\n", pais1, pib1, pais2, pib2);                  
                    resultado1 = pib1 > pib2 ? 1 :0;

                    if(resultado1 == 1){
                        printf(" %s Venceu ! Com pib de %f \n", pais1, pib1);
                        atrib1 = 1;
                    }else{
                        printf(" %s Venceu ! Com pib de %f \n", pais2, pib2);
                        atrib2 = !resultado1;
                    }

                break;    
            case 4: 
                    printf(" \n");
                    printf(" Você escolheu comparar a quantidade de Pontos Turisticos \n");
                    printf(" Os ponntos tudristicos de  %s tem um total de = %d  e %s tem um total de = %d\n", pais1, NumeroPontosTuristicos1, pais2, NumeroPontosTuristicos2);                  
                    resultado1 = NumeroPontosTuristicos1 > NumeroPontosTuristicos2 ? 1 : 0;

                    if(resultado1 == 1){
                        printf(" %s Venceu ! Tem %d pontos turisticos  \n", pais1, NumeroPontosTuristicos1);
                        atrib1 = 1;
                    }else{
                        printf(" %s Venceu ! Tem %d pontos turisticos  \n", pais2, NumeroPontosTuristicos2);
                        atrib2 = !resultado1;
                    }

                break;    
            case 5: 
                    printf(" \n");
                    printf(" Você escolheu comparar o DENSIDADE DEMOGRÁFICA \n");
                    printf(" A Densidade de  %s tem um total de = %1.f de habitantes por km2 e %s tem um total de = %.1f por Km2 \n", pais1, densidadeDemogratica1, pais2, densidaDemografica2);                  
                    resultado1 = densidadeDemogratica1 < densidaDemografica2 ? 1 : 0;                
                    
                        if(resultado1 == 1){
                            printf(" A Densidade demográfica de %s é menor com  %1.f  habitantes por km² por isso VENCEU\n",pais1, densidadeDemogratica1);
                           atrib1 = 1;
                        }else{
                            printf(" A Densidade demográfica de %s é menor com  %1.f  habitantes por km² por isso VENCEU\n",pais2, densidaDemografica2);
                           atrib2 = !resultado1;
                        }
            break;
                                    
            default: printf("OPÇÃO INVALIDA");
                break;
            }

                switch (comparacao2){ // esse segundo switch é para a comparação contraria a dos atributos
                    case 1: 
                            printf(" \n");
                            printf(" Você escolheu comparar qual tem a maior população! \n");
                            printf(" A população de  %s tem um total de = %f  e %s tem um total de = %f\n", pais1, Populacao1, pais2, Populacao2);                  
                            resultado2 = Populacao2 > Populacao1 ? 1 :0;            

                            if(resultado2 == 1){
                                printf(" %s Venceu ! Com população de %f ", pais2, Populacao2);
                                atrib2 = atrib2 + resultado2 ;
                            }else{
                                printf(" %s Venceu ! Com Populaçao de %f ", pais1, Populacao1);
                                atrib1 = !resultado2 + atrib1;
                            }
                        break;
                    case 2: // AREA
                            printf(" \n");
                            printf(" Você escolheu comparar a AREA \n");
                            printf(" A Area de  %s tem um total de = %f  e %s tem um total de = %f\n", pais1, area1, pais2, area2);
                            resultado2 = area2 > area1 ? 1 : 0;

                            if(resultado2 == 1){
                                printf(" %s venceu ! Com area de %f \n", pais2, area2);
                                atrib2 = atrib2 + resultado2;
                            }else{
                                printf(" %s venceu ! Com area de %f  \n", pais1, area1);
                                atrib1 = atrib1 + !resultado2  ;
                            }

                        break;    
                    case 3: //PIB
                            printf(" \n");
                            printf(" Você escolheu comparar o PIB \n");
                            printf(" O Pib de  %s tem um total de = %f  e %s tem um total de = %f\n", pais1, pib1, pais2, pib2);
                            resultado2 = pib2 > pib1 ? 1 : 0;

                            if(resultado2 == 1){
                                printf(" %s venceu ! Com Pib de %f \n", pais2, pib2);
                                atrib2 = atrib2 + resultado2;
                            }else{
                                printf(" %s venceu ! Com Pib de %f  \n", pais1, pib2);
                                atrib1 = atrib1 + !resultado2 ;
                            }

                        break;    
                    case 4: // PONTOS TURISTICOS
                            printf(" \n");
                            printf(" Você escolheu comparar a quantidade de Pontos Turisticos \n");
                            printf(" Os ponntos tudristicos de  %s tem um total de = %d  e %s tem um total de = %d\n", pais1, NumeroPontosTuristicos1, pais2, NumeroPontosTuristicos2);                  
                            resultado2 = NumeroPontosTuristicos2 > NumeroPontosTuristicos1 ? 1 : 0;

                            if(resultado2 == 1){
                                printf(" %s Venceu ! Tem %d pontos turisticos  \n", pais2, NumeroPontosTuristicos2);
                                atrib2 = atrib2 + resultado2 ;
                            }else{
                                printf(" %s Venceu ! Tem %d pontos turisticos  \n", pais1, NumeroPontosTuristicos1);
                                atrib1 = atrib1 + !resultado2 ;
                            }

                        break;    
                    case 5:  // DENSIDADE DEMOGRAFICA  quem tiver a menor ganha
                            printf(" \n");
                            printf(" Você escolheu comparar o DENSIDADE DEMOGRÁFICA \n");
                            printf(" A Densidade de  %s tem um total de = %1.f de habitantes por km2 e %s tem um total de = %.1f por Km2 \n", pais1, densidadeDemogratica1, pais2, densidaDemografica2);                  
                            resultado2 = densidaDemografica2 < densidadeDemogratica1 ? 1 : 0;                
                            
                                if(resultado2 == 1){
                                    printf(" A Densidade demográfica de %s é menor com  %1.f  habitantes por km² por isso VENCEU\n",pais2, densidaDemografica2);
                                    atrib2 = atrib1 + resultado2;
                                }else{
                                    printf(" A Densidade demográfica de %s é menor com  %1.f  habitantes por km² por isso VENCEU\n",pais1, densidadeDemogratica1);
                                    atrib1 =  atrib1 + !resultado2; // para que no final posso comparar
                                }
                    break;
                                            
                    default: printf("OPÇÃO INVALIDA \n ");
                        break;
                                                                     
                    }
                          
                printf("\n");
                    //
                    // esse if é para efetuas a comparação de quem venceu em mais atributos ou empatrou
                    //
                    if (atrib1 > atrib2){
                        printf("| %s é o Grande vencedor \n",  pais1);
                    }else if ( atrib2 > atrib1){
                        printf("| %s é o Grande vencedor \n", pais2);
                    }else{
                        printf("| EMPATE \n");
                    }
                    

    default: printf(" VOCÊ SAIU DO JOGO \n");
    break;
    }
return 0;

}
