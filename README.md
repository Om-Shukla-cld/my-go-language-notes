# my-go-language-notes


#println and printf

package main

import "fmt"

func main() {
	age := 23
	name := "om"
	height := 9.2233

	fmt.Println("age:", age, "height:", height, "name:", name)
	fmt.Println("hello world") // println jo hai kaheen par bhi use karoge to vo apne aap new line me hi output dega

	fmt.Printf("height is %2f\n", height)
	fmt.Printf("age is %d\n", age)           // Print f ke case me tumhe \n lagana hi apdega kyuki nhi lagaoge to ek hi line to statement aajyega
	fmt.Printf("Type of name is %T\n", name) // YE %T DATAYPE PATA AKRNE KE LIYE HAI KISI BHI VARIABLE KA
	fmt.Printf("Name: %s, Age: %d, Height: %.2f\n", name, age, height)  // ye format specifier se ham ek dusre ka reference de kste hAI
}

# to take input from user 
package main

import (
	"bufio"
	"fmt"
	"os"
)

func main() {
fmt.Println("what is your name ")
var name string
fmt.Scan(&name)      // input lene ke liye ek naya string banaya  lekin  ye ek word hi padh skta hai jaise space dekhega wahan end ho jayega like om but not shukla
fmt.Println("hello MR.", name)    // usko print karaya name ka reference dekar

dusra tareeka

reader := bufio.NewReader(os.Stdin)   // creates a new buffered reader that reads  from the standard input
name, _ := reader.ReadString('\n')   // reads line from the input until it encounter new line
fmt.Println("HELLO MR.", name)
}

# understanding function

package main

import "fmt"

func simplefunction() {
	fmt.Println("hello om")
}

func add(a, b int) int {    // dusra int hamne output ke liye use kiya   // curly braces bhi yaheen se lagana padega go me
	return a + b
}

func main() {
	fmt.Println("mausam bada saandar")
/	simplefunction()

/	ans := add(3, 4)           // dobara se function call kiya
fmt.Println("add of two number is", ans)

# ERROR HANDLING

package main

import "fmt"

func divide(a, b float64) (float64, error) {
	if b == 0 {
		return 0, fmt.Errorf("denominator must not be zero")
	}
	return a / b, nil

}

func main() {
	fmt.Println("started error handling int the function")
	ans, err := divide(10, 2)
	if err != nil {
		fmt.Println("error handling")
	}
	fmt.Println("division of two number is", ans)

		//ans, _ := divide(10,2)
		//fmt.Println("division of two number is ",ans) // agr aap koi error handling na karna  chAH RHE HO
	}

}
#UNDERSCOR KA USE \
//AGAR VARIABLE DECLARE KIYA HAI AUR USE USE NHI KIYA  TO COMPILATION ERROR AATA HAI  USKO AVAOID KARNE KE LIYE _ KA USE HOTA HAI 

package main
import "fmt"

func main(){
a,_ := 10,20  //yahan 20 ko ingnore kiya gya hai 
fmt.Println(a)  //sirf a ka use  ho rha hai 

# MAKING ARRAY

package main //
import "fmt"

func main() {
	// fmt.Println("we are learning arrays in Golang")

	// // Correct way to declare and initialize an array of strings
	// var name [5]string // space after "var name" is conventional
	// name[0] = "om"     // use = for assignment, not :=
	// name[2] = "shukla" // use = for assignment, not :=
	// fmt.Println("my name is:", name)

	// // Correct array initialization (this part was fine)
	// var numbers = [5]int{1, 2, 3, 4, 5}
	// fmt.Println("numbers is:", numbers)

	var name [5]string // jo bhi dataype yahan likhoge uska by default value hi output me show hoga like int me 0 aur bool me false aur string me kuch nhi
	name[0] = "om"
	name[4] = "shukla"

	fmt.Println("name is:", name)
	fmt.Printf("name is %q\n", name)   // quotation aajayega  empty strings par
}


OUTPUT : name is: [om    shukla]
name is ["om" "" "" "" "shukla"]
