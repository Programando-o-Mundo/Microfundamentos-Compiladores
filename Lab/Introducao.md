# Introducao

Nesta primeira aula iremos começar a fazer os primeiros componentes do nosso Compilador, que no caso seria, pegar as linhas do nosso arquivo fonte, e a classe 
do Compilador.

# Extraindo o texto do arquivo fonte

Primeiramente antes de começar o processo de Compilação, nós iremos precisar de pegar o nosso arquivo fonte, para o meu caso decidi ela será extraído 
fazendo leitura de arquivo, usando as bibliotecas leitura de arquivo em C++.

```c++ 
#include<iostream>
#include<fstream>
#include<vector>

std::vector<std::string> get_file_lines(std::string file_path);

int main(int argc, char* argv[]) {
  
    if (argc < 1) {
      std::cout << "Error! No file specified!" << "\n";
      return -1;
    }

    std::vector<std::string> file_lines = get_file_lines(std::string(argv[1]));
}

std::vector<std::string> get_file_lines(std::string file_path) {
    std::fstream file;
    file.open(file_path, std::ios::in);

    std::vector<std::string> lines;
    std::string curr_line = "";

    if (file.is_open()) {
        while (std::getline(file, curr_line)) 
          lines.push_back(curr_line);

        file.close();
    } else {
        std::cout << "Erro! the file does not " << file_path << "exist!" << "\n";
        exit(1);
    }
    
    return lines;
}
``` 

Caso este código esteja confuso para você, dê uma olhada na documentação do das bibliotecas do [std::vector](https://en.cppreference.com/w/cpp/container/vector) e do 
[std::fstream](https://linuxhint.com/use-cpp-fstream/), mas em resumo, se você olhar na função *main* teremos como resultado o vetor **file_lines** que irá conter
em cada posição do vetor as linhas do nosso programa fonte. Nós podemos confirmar isso, se imprimirmos o resultado disso na tela usando um *for* loop, dessa maneira:

```c++
int main(int argc, char* argv[]) {
  
    if (argc < 1) {
      std::cout << "Error! No file specified!" << "\n";
      return -1;
    }

    std::vector<std::string> file_lines = get_file_lines(std::string(argv[1]));
    
    for (auto line : file_lines) {
        std::cout << line << "\n";
    }
}
