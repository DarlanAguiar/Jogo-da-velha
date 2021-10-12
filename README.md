<! DOCTYPE html >
< html  lang = " pt-br " >
< cabeça >
    < meta  charset = " UTF-8 " >
    < meta  http-equiv = " X-UA-Compatible " content = " IE = edge " >
    < meta  name = " viewport " content = " width = device-width, initial-scale = 1.0 " >
    
    < title > Jogo da velha </ title >
    < estilo >
        corpo {
            
            imagem de fundo :  gradiente linear ( 45 graus ,  # 331BFA ,  # 5817E6 ,  # B31CE6 );
            família da fonte : Arial , Helvetica , sans-serif;
            tamanho da fonte :  15 pt ;
            cor : preto;
        }

        . regras {
            cor : branco;
            sombra do texto :  2 px  2 px  1 px preto
        }

        div {
            alinhamento de texto : centro;
        }

        h1 {
            raio da borda :  10 px ;
            cor de fundo :  rgba ( 255 ,  255 ,  255 ,  0,186 );
            largura :  290 px ;
            margem :  10 px auto;
            sombra do texto :  2 px  2 px  2 px branca;
        }

        header {

            alinhamento de texto : centro;
            peso da fonte : negrito;
           

        }
        p {
            margem : automático;
            cor : branco;
            sombra do texto :  1 px  1 px  1 px preta;
        }
        span {
            tamanho da fonte :  30 px ;
            sombra do texto :  2 px  2 px  2 px vermelho;
        }

        seção {
            fundo : branco;
            raio da borda :  10 px ;
            preenchimento :  15 px ;
            largura :  330 px ;
            margem : automático;
            sombra da caixa :  5 px  5 px  10 px  rgba ( 0 ,  0 ,  0 ,  0,638 );
        }

        rodapé {
            cor : branco;
            alinhamento de texto : centro;
            margem : automático;
            sombra do texto :  1 px  1 px  1 px preta;
            
        }
        rodapé  p {
            largura :  200 px ;
            margem : 15 px auto;
            fundo :  rgba ( 0 ,  0 ,  0 ,  0,207 );
            raio da borda :  7 px ;
        }
        . recomecar {
            alinhamento de texto : centro;
            margem : automático;
            cor : branco;
            tamanho da fonte :  15 px ;
            sombra do texto :  1 px  1 px  1 px preta;
        }

        . caixa {
            largura :  50 px ;
            altura :  50 px ;
            tamanho da fonte :  50 px ;
            padding-left :  25 px ;
            margem superior :  4 px ;
        
        }
        a {
            decoração de texto : nenhum;
            cor : branco;
        }

    </ estilo >
</ head >

< corpo >
    < cabeçalho >
        < h1 > Jogo da Velha </ h1 >
        < p  class = " regras " > Para jogar utilizar letra X e letra O </ p >
        < p  data-troca = "" > Vez do jogador < span > X </ span > </ p >
    </ header >
        
    < seção >
        
        < div > < input  id = " id1-1 " data-a1 = "" class = " caixa " type = " text " onkeyup = " verifica (event) " >
            < input  id = " id1-2 " data-a2 = "" class = " caixa " type = " text " onkeyup = " verifica (evento) " >
            < input  id = " id1-3 " data-a3 = "" class = " caixa " type = " text " onkeyup = " verifica (evento) " >
        </ div >
            
        < div >
            < div > < input  id = " id2-1 " data-b1 = "" class = " caixa " type = " text " onkeyup = " verifica (event) " >
                < input  id = " id2-2 " data-b2 = "" class = " caixa " type = " text " onkeyup = " verifica (evento) " >
                < input  id = " id2-3 "   data-b3 = "" class = " caixa " type = " text " onkeyup = " verifica (evento) " >
            </ div >
            
        </ div >
             
        < div >
            < div > < input  id = " id3-1 " data-c1 = "" class = " caixa " type = " text " onkeyup = " verifica (event) " >
                < input  id = " id3-2 " data-c2 = "" class = " caixa " type = " text " onkeyup = " verifica (evento) " >
                < input  id = " id3-3 " data-c3 = "" class = " caixa " type = " text " onkeyup = " verifica (evento) " >
            </ div >
            
        </ div >
    
    </ seção >
    < p  class = " recomecar " > Para recomeçar arraste o dedo para baixo </ p >



   
    < footer  data-texte = "" >
        < A  href = " https://www.facebook.com/darlan.aguiar.165 " >
            < p > & copy; Dr.Gelo Software & # x2122 </ p >
        </ a >
    </ rodapé >



    < script >
        
        var  vezDoX  =  true ;
        var  numeroDeJogadas  =  0 ;
        var  houveGanhador  =  falso ;

        função  jogadorDaVez ( )  {
            return  vezDoX ? "x" : "o" ;
        }
        
        função  jogadorDaVezMostra ( )  {
            return  vezDoX ? "o" : "x" ;
        }

         verificação de função ( e ) {
            const  valorDigitado  =  e . alvo . valor ;
            if  ( valorDigitado . comprimento  ===  0 )  {
                retorno ;
            }

            if  ( valorDigitado . toLowerCase ( )  ! ==  jogadorDaVez ( ) ) {
                alerta ( "Não digitou Correto" ) ;
                e . alvo . valor  =  '' ;
                retorno ;
            }

            numeroDeJogadas ++ ;
            verifica2 ( ) ;
            vezDoX  =  ! vezDoX ;
        }
            
        function  saoIguais ( a ,  b ,  c )  {
            retornar  a . valor . comprimento  >  0  &&  a . valor  ===  b . valor  &&  a . valor  ===  c . valor ;
        }

        função  verifica2 ( ) {
            
            var  a1  =  documento . querySelector ( "[data-a1]" ) ;
            var  a2  =  documento . querySelector ( "[data-a2]" ) ;
            var  a3  =  documento . querySelector ( "[data-a3]" ) ;
            var  b1  =  documento . querySelector ( "[data-b1]" ) ;
            var  b2  =  documento . querySelector ( "[data-b2]" ) ;
            var  b3  =  documento . querySelector ( "[data-b3]" ) ;
            var  c1  =  documento . querySelector ( "[data-c1]" ) ;
            var  c2  =  documento . querySelector ( "[data-c2]" ) ;
            var  c3  =  documento . querySelector ( "[data-c3]" ) ;

            var  vezJogador  =  documento . querySelector ( "[troca de dados]" ) ;

            vezJogador . innerHTML  =  `Vez do jogador <span> $ { jogadorDaVezMostra ( ) } </span>`
        
            houveGanhador  =  saoIguais ( a1 ,  a2 ,  a3 )  ||
                Sãoguais ( b1 ,  b2 ,  b3 )   ||
                Sãoguais ( c1 ,  c2 ,  c3 )  ||
                sãoguais ( a1 ,  b1 ,  c1 )  ||
                sãoguais ( a2 ,  b2 ,  c2 )  ||
                sãoguais ( a3 ,  b3 ,  c3 )  ||
                Sãoguais ( a1 ,  b2 ,  c3 )  ||
                saoIguais ( a3 ,  b2 ,  c1 ) ;

            
            se  ( houveGanhador ) {
                alerta ( `O ganhador foi $ { jogadorDaVez ( ) } .` ) ;
                documento . localização . recarregar ( verdadeiro )
            }  else  {
                if ( numeroDeJogadas  ===  9 )  {
                    alerta ( "Não ouve ganhador, corre novamente." )
                    documento . localização . recarregar ( verdadeiro )
                }
            }
        }

    </ script >



</ body >
</ html >
© 2021 GitHub, Inc.
Termos
Privacidade
Segurança
Status
Docs
Entre em contato com o GitHub
Preços
API
Treinamento
Blog
Cerca de
