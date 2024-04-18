
# js-challenges
# Collection of different JavaScript challenges with my solutions.


1. ### Valid Palindrome ( solution in Big O (log n) )

    <details>
    <summary>solution for this challenge</summary>
    <br>
    
    ```javascript
    function palindromeCheck( str ){
    
    	let isPalindrome = false;
    	let strLength = str.length;
    
    	for ( let i=0; i < strLength; i++){
    		console.log('i =', i , "  ", 'strLength - 1 - i =', strLength - 1 - i);
    
    		if (str[i] == str[strLength - 1 - i]){
    			isPalindrome = true;
    		}else{
    			isPalindrome = false;
    			break;
    		}
    
    		/*
    		* Once the left pointer and the right pointer reach the middle 
    		* of the current string we can break the loop. The middle of 
    		* the string can be one character if we have add number 
    		* of characters or for even number of chars if position of 
    		* the left pointer minus position of the right pointer === 1 that 
    		* means those pointers are at adjacent elements and we can break 
    		* the loop because at this point we've checked all characters
			*/
    		
    		if(i == strLength - 1 - i || strLength - 1 - i - i == 1){
    			console.log('pointers reached the middle of the string');
    			break;
    		}
    	}
    
    	return isPalindrome;
    }
    
    palindromeCheck( 'abcdcba' ) // true
    
    palindromeCheck( 'abcddcba' ) // true
    
    palindromeCheck( 'abcdfcba' ) // false
    ```
        
    </details>






2. ### Reverse the string ( solution in Big O (log n) )

    <details>
    <summary>solution for this challenge</summary>
    <br>
    
    ```javascript
    function reverse (str){

    let tempStr1 = "";
    let tempStr2 = "";
    let middleOfStr = Math.floor(str.length / 2) - 1;
    let rightPointer = middleOfStr;

    for ( let i = str.length - 1; i > middleOfStr; i--){
        console.log('i =', i , " ", 'rightPointer =', rightPointer);

        tempStr1 += str[i];

        if (-1 !== rightPointer){
            tempStr2 += str[rightPointer];
            rightPointer--;
        }
    }
    return tempStr1 + tempStr2;
    }

    reverse("abcdef");  // 'fedcba'

    reverse("javaScript");  // 'tpircSavaj'

    reverse("Hello, world!");  // '!dlrow ,olleH'
    ```
        
    </details>




