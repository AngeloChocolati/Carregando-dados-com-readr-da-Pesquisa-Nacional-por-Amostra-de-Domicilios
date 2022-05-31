# Carregando-dados-com-readr-da-Pesquisa-Nacional-por-Amostra-de-Domicilios
# Neste codigo vc vera aplicações com as principais funcoes do "readr" na base de dados da PNAD 2015


library(readr)


# O que esta sendo feito abaixo é nada mais que o casamento de  3 variaveis: "tamanho", "nome" e "tipo"
# eu criei esses nomes (tamanho, nome, tipo) para cada vetor.

tamanho <- c(4, 8, 3, 2, 2, 2, 1, 1, 1, 1, 2, 2, 1, 12, 12, 1, 1, 1, 1,
             1, 1, 1, 2, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 2, 2, 1, 1,
             1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 
             2, 2, 4, 2, 12, 3, 12, 6, 9, 3, 5, 12, 4, 7, 7, 2, 12, 2, 1, 1, 7, 5, 8)

nome <- c('V0101','V0102','V0103', 'V0104','V0105','V0106','V0201','V0202','V0203',
          'V0204', 'V0205','V0206','V0207','V0208','V0209','V0210','V0211','V0212',
          'V0213', 'V0214','V0215','V0216','V2016','V0217','V0218','V0219','V0220',
          'V2020','V0221','V0222', 'V0223','V0224','V0225','V0226','V0227', 'V02270',
          'V02271','V02272','V02273','V02274', 'V2027','V0228','V0229','V0230', 'V0231',
          'V0232','V02321','V02322','V02323','V02324','V02325','V02326', 'V02327','V02424',
          'V02425','V02426', 'V2032','V4105','V4107','V4600','V4601','V4602','V4604', 'V4605',
          'V4606', 'V4607','V4608','V4609','V4610','V4611', 'V4614','UPA','V4617','V4618','V4620', 
          'V4621','V4622','V4624','V4628','V4632', 'V4633','V9992')

# nesta variavel eu resolvi atribuir esse nome como "tipo" e repare que foi adicionado um recurso chamado "paste0" ele serve para "quebrar" a linha do vetor
# como pode obeservar abaixo temos 3 linhas, pra que eu fiz isso? bom isso serve para quando vc tiver um vetor muito grande ai vc pode apenas as linhas do vetor sem o risco de retornar algum erro, ouseja, sem preuízo no seu código.
tipo <- paste0("ccccccccccnncnncccccccncccccccccc", 
               "ccccccccccccccccccccccccccccccncn", 
               "ccnnncnncncccncc")


# o str() serve para... (para esse script ainda não defini)            

str(tipo)

# Aperte Enter 
# Atribui o nome "euqfiz"

# nome_q_eu_atribui   <- read_fwf   ('C:/ local / local / local / arquivo.txt,   fwf_widths(  (tamanho), col_names = nome), col_types = tipo)
#
euqfiz <- read_fwf('C:/Users/UFMT/Downloads/t-nqray/pct/EST_microdata_3P_3Executivo/EST_microdata_GOV_Federal/EST_microdata_Ministérios/EST_microdata_Ministério da Economia/EST_microdata_IBGE/EST_microdata_pnad/DOM2015.txt', fwf_widths((tamanho), col_names = nome), col_types = tipo)


names(euqfiz)
str(euqfiz)

#------------------------ finish and working -------------------------
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣯⣥⣤⣾⠟⡛⠿⠿⣭⣻⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣿⡟⣿⣽⡟⡏⢩⣦⡝⠋⢸⣶⠄⢲⡟⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣯⣷⣿⣿⣿⣿⣿⣿⣿⣿⣷⣶⣌⡳⣜⢿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡇⢀⡛⢌⢿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⢸⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠁⠄⠙⠌⣸⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⡿⠉⠉⠉⠉⢿⣿⣿⣿⠏⠉⠉⠉⠉⠉⠆⠄⠁⠄⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⡗⠫⠿⠆⠄⠸⢿⣿⣿⠂⠒⠲⡿⠛⠛⠂⠄⠄⢠⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⡛⣧⡔⠢⠴⣃⣠⣼⣿⣧⡀⠘⢢⣀⠄⠄⠄⠄⠄⢈⠁⢿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣶⣿⠄⠄⠄⣸⠆⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣿⣿⡿⣿⣿⣿⣿⣼⢿⣿⣿⣿⣿⡀⠄⠘⡀⢠⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⡌⠿⣫⣿⣦⠬⢭⣥⣶⣬⣾⣿⢿⣿⡟⠄⢀⣿⣶⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣧⠘⣉⠛⢻⣛⣛⣛⣻⡶⠮⠙⠃⣉⠄⠄⢸⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⡆⠸⣿⣶⢾⣿⣯⣤⣄⣀⣾⡟⠄⠄⠄⢸⣿⣿⣿⣿⣿⣿⣿⣿
⠟⠿⠿⠿⠿⢿⣷⠄⣿⣿⣎⣹⢻⣿⣿⡿⡿⠁⠄⠄⠄⢸⣿⣿⣿⣿⣿⣿⣿⣿
⠄⠄⠄⠄⠄⠄⠄⣠⠘⣿⣿⣿⣿⣿⣿⡟⠁⣀⣀⣀⠄⠘⠿⣿⣿⣿⣿⣿⣿⣿
