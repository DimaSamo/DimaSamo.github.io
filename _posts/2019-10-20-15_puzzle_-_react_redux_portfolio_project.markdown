---
layout: post
title:      "15 Puzzle - React/Redux Portfolio Project"
date:       2019-10-20 09:26:26 +0000
permalink:  15_puzzle_-_react_redux_portfolio_project
---


Phew... Well today is the day that I finished my final project for the Flatiron School!
So this time around approaching the project I didn't really have many ideas of what to do, so naturally as I'm a gamer myself, I decided to create a small board game application the 15 puzzle.

The goal of the game is to rearrange the board of numbers to be sorted from 1-15 while only having one tile free: ![](https://i.imgur.com/kMZGyAC.png)

As with any other project the most difficult part was getting started somewhere, so I just went straight into it and started working on the board. Configuring the state of the board was pretty simple, just initializing an array of numbers from 1-15 and an empty spot, but then randomizing it was abit tricky, but I found a function to shuffle array elements that helped me out: 
```
function shuffle (a) {
    for (let i = a.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [a[i], a[j]] = [a[j], a[i]];
    }
    return a;
}
```

So after that I had to implement the board updating based on click on a specific tile, I wrote a function that checks if a tile is moveable based on the boards current state and the tiles index:


```
 function isMoveValid(board, index){
    switch (true) {
        case (board[index+1] === " "):
            return true
            
        case (board[index-1] === " "):
            return true
            
        case (board[index-4] === " "):
            return true   

        case (board[index+4] === " "):
        return true 
    
        default:
            return false;
    }
}
```

Once I've had most of the game logic setup, it was fairly simple, I had another function to check if the game is won against a perfectly sorted array.

I also added a leaderboard that utilizes the Rails backend API that I've setup, at the end of the game you can choose to submit your score (based on the amount of moves), I've used redux-thunk to be able to perform async actions to fetch data from my Rails API and display it on the leaderboard component.

All in all I feel like it has been a pretty fun experience, I always enjoy these project weeks and creating something from scratch as opposed to the labs where alot of the stuff is preset already, you do really get to practice the flow of the framework and improve the understanding of the material.
 


