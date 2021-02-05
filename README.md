
Com essa função, programadores de Arduino, ESP8266, ESP32 e outros microcontroladores podem resolver o problema de manipular stringa com caracteres especiais, que, geralmente causam erro.

//Exemplo

String original = "Thomé Lucás de Áraújó Ólíveíra çÇ Leão LEÃO você VOCÊ";

String convertido = "";

String removerAcentos(String texto){

    String comAcentos = "ÄÅÁÂÀÃäáâàãÉÊËÈéêëèÍÎÏÌíîïìÖÓÔÒÕöóôòõÜÚÛüúûùÇç";
    
    String semAcentos = "A A A A A A a a a a a E E E E e e e e I I I I i i i i O O O O O o o o o o U U U u u u u C c";
    
    for (int i = 0; i < comAcentos.length(); i++){
    
        texto.replace(comAcentos.substring(i, i+2), semAcentos.substring(i, i+1));
        
    }
    
    return texto;
    
}



void setup() {

  delay(1000);
  
  Serial.begin(115200);
  
  convertido = removerAcentos(original);
  
  Serial.println(original);
  
  Serial.println(convertido);
  
}


void loop() {


}
