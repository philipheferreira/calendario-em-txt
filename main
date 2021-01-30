#include <stdio.h>
#include<stdlib.h>
#include<locale.h>


int main(int argc, char** argv){
	setlocale(LC_ALL, "");
	int primeiraSemana(int ano); //chama a função para ser ativada no menu
	system("color 1D");
	
	FILE *calendario;
	calendario = fopen("C:\\Users\\phili\\OneDrive\\Documentos\\programacao\\linguagem c\\calendario\\calendario.txt", "w");
	
	int escolha;
	int ano, mes, dia, diasNoMes, diaSemana = 0, comecoDia; // ano é para definir os anos que fevereiro tem mais um dia. mes = usado pelo for para definir a quantidade de meses utilizando o meses para alocar cada nome com a posição no vetor criado no for. dia = define os dias em cada mês no vetor criado, sendo limitado os dias pelo mesDia, onde defini a data de termino de cada mês
	int mesDia[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31}; // são os dias maximos de cada mês, de janeiro a dezembro
	char *meses[] = {"Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho", "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro"};
	
	printf("\nColoque o ano que você deseja vizualizar: ");
	scanf("%i", &ano); // A variavel inteira ano ira receber o valor digitado pelo usuario 
	
	if((ano%4 == 0 && ano%100 != 0) || (ano %400 == 0)){ // basicamente informa que quando o ano for divisivel por 4 e 100 ou 400, então é para ativar o valor a baixo. Classificando anos bissestos
		mesDia[1] = 29; // em todo ano 4 o mês de fevereiro tem 29 dias, um dia a mais que o normal
	}
	
	comecoDia = primeiraSemana(ano); //usa o ano colocado pelo usuario como valor para função 
	
	for(mes = 0; mes < 12; mes++){ // foi utilizado um laço for para repitir os meses de janeiro a dezembro. foi criada uma variavel inteiro mês para o processo com o objetivo de posicionar os meses da variavel meses em cada local
		diasNoMes = mesDia[mes]; // diasNoMes faz o link entre os meses no vetor e mesDia que limita o fim de cada mes.
		printf("\n\n-----------------------%s-----------------------\n",meses[mes]);
		printf("\n   Dom  Seg  Ter  Qua  Qui  Sex  Sab\n");
		
	for(diaSemana = 0; diaSemana < comecoDia; diaSemana++){ 
		printf("     ");
	}
			
	// é de estrema importancia que o for de dias rode dentro do for mes, para que quando cada mes for ativado, o for haja em conjunto com cada mes que for iniciado e finalizado. Se ele for iniciado fora ele só tera efeito no ultimo mes, que é o mes de dezaembro
	for(dia = 1; dia <= diasNoMes; dia++){ // dia serão os dias dos meses plotados no calendario, começando pelo dia 1 que foi definindo e finalizando no dia 31
		printf("%5i", dia); // o 5 entre % e i é definido com os 5 espaços de distancia entre os numeros
		
	diaSemana = diaSemana + 1; //diaSemana começa sempre zerada como foi declarada a variavel, a formula adiciona um +1 ao ultimo valor de dia semana.
	
	if(diaSemana > 6){ //  Toda vez que diaSemana chegar a 6, é dado um espaço para organizar o calendario e depois no final é zerado o valor
		printf("\n");
		diaSemana = 0; 
	}
 comecoDia = diaSemana;
	}
	
	} 
	
	printf("\n\nDeseja salvar um arquivo de texto com o calendario gerado?\n1-Sim.\n2-Não.\nQualquer outro valor inserido o programa irá encerrar automaticamente.\n\nR=");
	scanf("%i", &escolha);
	switch(escolha){ 
	case 1: 
		
		//           arquivos referentes a criação de arquivo
	fprintf(calendario, "\n\n-----------------------%i-----------------------\n", ano);
	
	if((ano%4 == 0 && ano%100 != 0) || (ano %400 == 0)){ // basicamente informa que quando o ano for divisivel por 4 e 100 ou 400, então é para ativar o valor a baixo. Classificando anos bissestos
		mesDia[1] = 29; // em todo ano 4 o mês de fevereiro tem 29 dias, um dia a mais que o normal
	}
	
	comecoDia = primeiraSemana(ano); //usa o ano colocado pelo usuario como valor para função 
	
	for(mes = 0; mes < 12; mes++){ // foi utilizado um laço for para repitir os meses de janeiro a dezembro. foi criada uma variavel inteiro mês para o processo com o objetivo de posicionar os meses da variavel meses em cada local
		diasNoMes = mesDia[mes]; // diasNoMes faz o link entre os meses no vetor e mesDia que limita o fim de cada mes.
		fprintf(calendario,"\n\n-----------------------%s-----------------------\n",meses[mes]);
		fprintf(calendario,"\n   Dom  Seg  Ter  Qua  Qui  Sex  Sab\n");
		
	for(diaSemana = 0; diaSemana < comecoDia; diaSemana++){ 
		fprintf(calendario,"     ");
	}
			
	// é de estrema importancia que o for de dias rode dentro do for mes, para que quando cada mes for ativado, o for haja em conjunto com cada mes que for iniciado e finalizado. Se ele for iniciado fora ele só tera efeito no ultimo mes, que é o mes de dezaembro
	for(dia = 1; dia <= diasNoMes; dia++){ // dia serão os dias dos meses plotados no calendario, começando pelo dia 1 que foi definindo e finalizando no dia 31
		fprintf(calendario,"%5i", dia); // o 5 entre % e i é definido com os 5 espaços de distancia entre os numeros
		
	diaSemana = diaSemana + 1; //diaSemana começa sempre zerada como foi declarada a variavel, a formula adiciona um +1 ao ultimo valor de dia semana.
	
	if(diaSemana > 6){ //  Toda vez que diaSemana chegar a 6, é dado um espaço para organizar o calendario e depois no final é zerado o valor
		fprintf(calendario,"\n");
		diaSemana = 0; 
	}
 comecoDia = diaSemana;
	}
	
	}
	
	fclose(calendario);
		
		break;
	case 2: 
		printf("Agradecemos o uso do programa calendario, tenha um excelente dia");
		
		break;
	default: 
		printf("O programa irá fechar automaticamente, tenha um bom dia");
		break;
	}
	
	
}


int primeiraSemana(int ano){ // função para fazer a contagem dos ano
	
	int dia;
	dia = (((ano - 1) * 365) + ((ano - 1) /4) - ((ano - 1) / 100) + ((ano) / 400) + 1) %7;
	
	return dia;
}
