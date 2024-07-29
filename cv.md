# Nikita Sobol

---

## Contacts

-   **Location**: Minsk, Belarus
-   **Email**: soboln2006@gmail.com
-   **GitHub**: [SobolNikita](https://github.com/SobolNikita)
-   **Discord** [xlebyshek](https://discordapp.com/users/379293531036188683/)
-   **Codewars**: [xlebyshek](https://www.codewars.com/users/xlebyshek) **4 kyu**
-   **Codeforces**: [xlebyshek2020](https://codeforces.com/profile/xlebyshek2020) **1700 rating**

## About me

I am 18 years old and I have become a **student of BSUIR** in 2024. I have no experience in commercial development but I have good basic knowledge in web development. I also have a good base in **algorithms and data structures**. In 2024 I was engaged in the [school of algorithms from Yandex](https://education.yandex.ru/kruzhok) and became the winner of the Republican Olympiad in Informatics in Belarus. Now I am developing in the sphere of **front-end development** and soon I will reach junior level.

## Skills

-   HTML
-   CSS/SASS/SCSS
-   JavaScript (Fundamentals, ES6+, DOM, JSON, Asynchronous JavaScript)
-   C++ (Basic knowledge)
-   React (Basic)
-   Git, GitHub
-   Webpack (Basic)
-   Figma, Photoshop, **VSCode**, WebStrom, Sublime Text, etc.
-   Algorithms and data structures

## Code example

[Sudoku Solver solution (_3 kyu_) Codewars](https://www.codewars.com/kata/5296bc77afba8baa690002d7)

```javascript
function getSquare(i, j) {
    return Math.floor(i / 3) * 3 + Math.floor(j / 3);
}

function setValue(data, value, i, j, type) {
    data.board[i][j] = type === 1 ? value : 0;
    data.usedX[j][value] = type;
    data.usedY[i][value] = type;
    data.usedSquare[getSquare(i, j)][value] = type;
    data.zeroCnt += type === 1 ? -1 : 1;
}

function solve(data, line) {
    if (data.zeroCnt === 0) {
        return;
    }
    for (let i = line; i < 9; ++i) {
        for (let j = 0; j < 9; ++j) {
            if (data.board[i][j] === 0) {
                for (let value = 1; value <= 9; ++value) {
                    if (
                        data.usedX[j][value] === 0 &&
                        data.usedY[i][value] === 0 &&
                        data.usedSquare[getSquare(i, j)][value] === 0
                    ) {
                        setValue(data, value, i, j, 1);
                        if (data.zeroCnt === 0) {
                            return;
                        }
                        solve(data, i);
                        if (data.zeroCnt === 0) {
                            return;
                        }
                        setValue(data, value, i, j, 0);
                    }
                }
                return;
            }
        }
    }
}

function sudoku(puzzle) {
    let zeroCnt = 0;
    let usedX = new Array(9);
    let usedY = new Array(9);
    let usedSquare = new Array(9);

    for (let i = 0; i < 9; ++i) {
        usedX[i] = new Array(10);
        usedY[i] = new Array(10);
        usedSquare[i] = new Array(10);
        for (let j = 0; j <= 9; ++j) {
            usedX[i][j] = 0;
            usedY[i][j] = 0;
            usedSquare[i][j] = 0;
        }
    }
    for (let i = 0; i < 9; ++i) {
        for (let j = 0; j < 9; ++j) {
            if (puzzle[i][j] === 0) {
                zeroCnt++;
            } else {
                if (
                    usedX[j][puzzle[i][j]] === 1 ||
                    usedY[i][puzzle[i][j]] === 1 ||
                    usedSquare[getSquare(i, j)][puzzle[i][j]] === 1
                ) {
                    return "Puzzle has no solution";
                }
                usedX[j][puzzle[i][j]] = 1;
                usedY[i][puzzle[i][j]] = 1;
                usedSquare[getSquare(i, j)][puzzle[i][j]] = 1;
            }
        }
    }
    let data = {
        board: puzzle,
        zeroCnt,
        usedX,
        usedY,
        usedSquare,
    };
    solve(data, 0);
    if (data.zeroCnt != 0) {
        return "Puzzle has no solution";
    }
    return data.board;
}

var puzzle = [
    [5, 3, 0, 0, 7, 0, 0, 0, 0],
    [6, 0, 0, 1, 9, 5, 0, 0, 0],
    [0, 9, 8, 0, 0, 0, 0, 6, 0],
    [8, 0, 0, 0, 6, 0, 0, 0, 3],
    [4, 0, 0, 8, 0, 3, 0, 0, 1],
    [7, 0, 0, 0, 2, 0, 0, 0, 6],
    [0, 6, 0, 0, 0, 0, 2, 8, 0],
    [0, 0, 0, 4, 1, 9, 0, 0, 5],
    [0, 0, 0, 0, 8, 0, 0, 7, 9],
];

console.log(sudoku(puzzle));
```

## Experience

Worked on small personal projects, created small projects from lessons using **HTML, CSS, JS, REACT, TypeScript (once)**, various project builders and libraries

## Education

-   **Belarusian State University of Informatics and Radioelectronics**
    -   _Faculty of Computer Systems and Networks (2024 - 2028)_

## Languages

-   **Russian** (native)
-   **Belarusian**
    -   ##**English** (Intermediate)
        -   C1 [EFSET result](https://cert.efset.org/qztyTX)
        -   B1 [EPAM examinator result](https://ibb.co/YpNqY83)
