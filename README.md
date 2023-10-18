# firstjsproject
here we wil talk about how i made this project <br>

in js we wil select the input tag and the container <br>
1. input tag in which we will type the no. of words whose paragraph is to be generated<br>
2. container which is class id of a div inside which our header file is present<br>

const input = document.getElementById("numOfwords");<br>
const container = document.querySelector(".container");<br>

now we will make a function suppose generateWord in which we will pass how much the length of the word is required and we will make a variable named text which  is empty<br>
now we will run a loop upto the length of word and we will add alphabets one by one to the variable text. suppose we need 5 characters word so one by one these words will be added<br>
which will be random

const generateWord = (n) => {<br>
  let text = "";<br>
  const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";<br>

  for (let i = 0; i < n; ++i) {<br>
    const random = (Math.random() * 25).toFixed(0);// tofixed to not print the decimal value<br>
    text += letters[random];<br>
  }<br>

  return text;<br>
};<br>



now words part is complete so in order to make a para we will again make a function inside the function we will take the value whatever user writes that this much no. of words para needs to be generated <br>
now we make an element with p tag with name data which wil be empty then we will run a loop till no. of words lets suppose 200 words someone entered then in every iteration what happens is we call generateWord <br>
and we passed random no. in it which will generate 1-15 letters word and will be saved in data  then we will add space<br>

const generatePara = () => {<br>
  const numOfWords = Number(input.value);<br>
  const para = document.createElement("p");<br>

  let data = "";<br>

  for (let i = 0; i < numOfWords; ++i) {<br>
    const randomNumber = (Math.random() * 15).toFixed(0);<br>
    data += generateWord(randomNumber);<br>
    data += " ";<br>
  }<br>

After the loop ends we will have a string named data which will be our para the para which we created we will add the data wo its innerText <br>
 para.innerText = data; <br>
 now we will add class for the para which will be named as paras so that it will get css properties<br>
para.setAttribute("class", "paras");<br>
in the end we will append in container <br>
 container.append(para);<br>



# firstjsproject
