# Rock-Paper-Scissor

A simple implementation of the classic game Rock, Paper, Scissors in Go, with a basic web interface.

## Contents

1. **go.mod**:
   This code represents a module declaration for a Go (Golang) application named "myapp". The line `go 1.18` indicates that the application requires Go version 1.18 or higher to run. This ensures that the application can utilize the features and improvements introduced in version 1.18 while maintaining compatibility with the language specifications.

2. **index.html**:
   This HTML file implements a simple Rock, Paper, Scissors game. It includes buttons for the player to choose their move and displays the computer's choice and the outcome of each round. The styling is done using Tailwind CSS and Bootstrap Icons. When a player selects a move, it triggers a JavaScript function (`choose(x)`) which sends a request to a server-side endpoint (`/play?c=`) with the player's choice (`x`). The response from the server is then displayed to the user, showing the player's and computer's choices, as well as the result of the round.

3. **main.go**:
   This Go code defines a straightforward web application designed for playing the classic game of Rock, Paper, Scissors. It consists of various components: a handler function, `homePage`, responsible for rendering the HTML template; another handler function, `playRound`, which processes requests for playing rounds of the game by receiving the player's choice as a query parameter, then utilizing the functionality provided by the `rps` package to determine the result of the round, and finally returning the outcome as JSON data. The core logic for the game is encapsulated within the `rps` package. The `main` function orchestrates the application, setting up HTTP routes ("/play" and "/") and initiating a web server that listens for incoming connections on port 8080. Additionally, a utility function, `renderTemplate`, is provided to facilitate the rendering of HTML templates. This architecture ensures a separation of concerns, with clear delineation between the web server logic, game mechanics, and presentation layer, enhancing maintainability and scalability of the application.

## Sub-Directory

### rps

1. *rps.go*:
   The `rps` package in Go implements the logic for playing Rock, Paper, Scissors. It defines constants for the game's options (ROCK, PAPER, SCISSORS) and outcomes (PLAYERWINS, COMPUTERWINS, DRAW). The `PlayRound` function takes the player's choice as input, randomly generates the computer's choice, and then determines the winner based on the game rules. It returns a `Round` struct containing the winner (PLAYERWINS, COMPUTERWINS, DRAW), the computer's choice, and the result of the round. The winner is determined by comparing the player's choice to the computer's choice according to the cyclic nature of the game (ROCK beats SCISSORS, SCISSORS beats PAPER, PAPER beats ROCK). This package provides the essential game mechanics necessary for the web application to function effectively.

## How to Play

1. Clone this repository to your local machine.
2. Build and run the web server using the `go run` command.
3. Visit `http://localhost:8080` in your web browser.
4. Click on one of the buttons to choose rock, paper, or scissors.
5. See the result of the round displayed on the page.

## Dependency

In this Go application, the only external dependency explicitly used is the standard library package `"math/rand"`, which is imported to generate random numbers for the computer's choice in the Rock, Paper, Scissors game. However, there are implicit dependencies on other standard library packages such as `"time"` used for seeding the random number generator. Additionally, there is a dependency on the HTTP server functionality provided by the `"net/http"` package, utilized for handling incoming HTTP requests and serving responses. Furthermore, the HTML/template package is employed for rendering HTML templates in the web application. While not explicitly listed, these standard library packages constitute dependencies for the application's functionality.

## Author
This project was created by [Samyam](https://github.com/samyam81).
