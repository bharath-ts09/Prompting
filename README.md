************Prompting Techniques************
--------------------------------------------
******Zero Shot Prompting******
---------------------------------




**Classification**
-------------------


**Objective**
Identify if the vacation was Neutral, Positive or Negetive - Version 1


**Prompt**
Text: I think the vacation is okay.
Sentiment:


**Response**
Sentiment: Neutral


****Translation****
----------------------


**Objective**
English to Spanish translation

**Prompt**
Translate the following English text to Spanish
Text: Hello! How are you doing today

**Response**
¡Hola! ¿Cómo estás hoy?



****Summarization****
-----------------------


**Objective**
Summarize the following paragraph in one sentence

**Prompt**
Summarize the following paragraph in one sentence:

Antibiotics target specific features of bacterial cells that are not found in human cells, which helps to minimize damage to the host. Common mechanisms include:
- **Cell wall synthesis inhibition**: Antibiotics like penicillin prevent bacteria from forming their protective cell walls, leading to cell lysis.
- **Protein synthesis inhibition**: Some antibiotics target the ribosomes of bacteria, disrupting their ability to produce proteins essential for growth and function.
- **Nucleic acid synthesis inhibition**: Certain antibiotics interfere with the processes that allow bacteria to replicate their DNA and RNA.
- **Metabolic pathway interference**: Some antibiotics disrupt pathways that bacteria use to synthesize essential nutrients.



**Response**
Antibiotics work by targeting unique bacterial structures and processes, such as cell wall formation, protein synthesis, DNA/RNA replication, and essential metabolic pathways, minimizing harm to human cells.



****Explanation****
--------------------


**Objective**
Explain Zero shot prompting to a small kid

**Prompt**
Explain Zero shot prompting as you are explaining to a 10 year old


**Response**
Okay, imagine you’re asking me a question about something I’ve never been told before, like, “What’s the capital of Mars?” Even though I’ve never been taught about Mars’ capital, I try my best to guess the answer using what I already know. That’s kind of like zero-shot prompting — when you ask me to do something without giving me any examples first, and I figure it out based on what I’ve learned!

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

****Few Shot Prompting****
-------------------------------

****Classification****
-----------------------

**Objective**
Classify to appropriate sentiment based on the below examples

**Prompt**
Perform the sentiment classification based on the provided inputs. Classify it either negative or positive

### Examples ###

The presentation was awesome!! Positive
The game was really bad!! Negetive
What a horrible play !!



**Response**
Negetive


****Specification****
-----------------------

**Objective**
Extract the Technical Specification from the JSON format

**Prompt**
Extract the technical specifications from the text below in JSON format.

<Example>
Input : Galaxy S24 Ultra, CPU Speed 3.39 GHz, CPU Type Octa Core, Size 172.5mm (6.8" full rectangle), Resolution 3120 x 1440 (Quad HD+), Rear Camera 200MP + 50 MP, Zoom Optical Zoom 3x and 5x, Optical quality Zoom 2x and 10x (Enabled by Adaptive Pixel sensor), Storage 512GB, Memory 12GB, Number of SIM Dual-SIM, Android OS

OUTPUT:
{
	"product":"Galaxy S24 Ultra",
	"Processor CPU Speed":"3.39 GHz",
	"Processor CPU Type":"Octa Core",
	"Display size":"172.5mm (6.8" full rectangle)",
	"Display Resolution":"3120 x 1440 (Quad HD+)",
	"Camera":"200MP + 50 MP",
	"Camera Zoom":"Optical Zoom 3x and 5x, Optical quality Zoom 2x and 10x (Enabled by Adaptive Pixel sensor)",
	"Storage/Memory":"512GB/12GB",
	"SIM":"Dual-SIM",
	"OS":"Android"
}

Input : Apple iPhone 15 Pro Max, Hexa-core (2x3.78 GHz + 4x2.11 GHz), Size 6.7 inches, 1290 x 2796 pixels, Camera 48MP, Storage 512GB, Memory 8GB, iOS 17 OS

OUTPUT:



**Response**
{
	"product": "Apple iPhone 15 Pro Max",
	"Processor CPU Speed": "Hexa-core (2x3.78 GHz + 4x2.11 GHz)",
	"Display size": "6.7 inches",
	"Display Resolution": "1290 x 2796 pixels",
	"Camera": "48MP",
	"Storage/Memory": "512GB/8GB",
	"OS": "iOS 17"
}

------------------------------------------------------------------------------------------------------------------------------------------------------------------------

********Chain of Thought Prompting********
-------------------------------------------

****Few Shot Chain of thought****

**Objective**

With an example provided perform multi step calculations

**Prompt**

Q: If there are 5 Bananas, 2 Apple with Raju. Raju ate 2 banana and 1 apple. He later bought 3 Pear. How many fruits does he have in the end
A: Raju starts with 5 Bananas and 2 apples, total 7 fruits. He eats 2 bananas and 1 apple, he now has 3 bananas and 1 apple. He buys 3 pears, adding those 3 bananas + 1 apple + 3 pears = 7 fruits
Q: If there are 3 cars in the parking lot and 2 more cars arrive, Half an hour later 1 car leave. How many cars are remaining in the parking lot?
A:

**Response**

A: There are initially 3 cars in the parking lot. 🚗🚗🚗

2 more cars arrive → Now there are 5 cars. 🚗🚗🚗🚗🚗

1 car leaves after half an hour → 5 - 1 = 4 cars remaining. ✅

-------------------------------------------------------------

****Zero Shot Chain of thought****

**Objective**

Perform Zero shot Chain of thought using "Lets think step by step"

**Prompt**

Q: If there are 5 Bananas, 2 Apple with Raju. Raju ate 2 banana and 1 apple. He later bought 3 Pear. How many fruits does he have in the end
Lets think step by step 

**Response**

Sure! Let’s think step by step:

Starting fruits:

🍌 5 Bananas + 🍎 2 Apples = 7 fruits

Raju eats:

2 Bananas → 5 - 2 = 3 Bananas left

1 Apple → 2 - 1 = 1 Apple left

Fruits remaining after eating:

3 Bananas + 1 Apple = 4 fruits

Raju buys 3 Pears: 🍐🍐🍐

4 fruits + 3 Pears = 7 fruits

✅ Final count: 3 Bananas, 1 Apple, and 3 Pears = 7 fruits.


----------------------------------------------------------------------------------------------------------------------------------------------

****Auto-COT****

Auto-CoT consists of two main stages:

Stage 1): question clustering: partition questions of a given dataset into a few clusters
Stage 2): demonstration sampling: select a representative question from each cluster and generate its reasoning chain using Zero-Shot-CoT with simple heuristics

Code for Auto-COT is here below

https://github.com/amazon-science/auto-cot



-------------------------------------------------------------------------------------------------------------------------------------------------------

****Meta Prompting****
------------------------

**Objective**

How many circular prime are there below 1 million

**Prompt**

The number 197, is called a circular prime because all rotations of the digits: 197, 791, 719 are themselves prime.

There are thirteen such primes below 100 : 2,3,5,7,11,13,17,31,37,71,73,79 and 97

How many circular primes are there below one million?

Expert Python:
"""Use Python code to identify the numbers if they are prime"""

Expert Mathematician:
"""
Validate the numbers given by the code if those prime numbers identified by code is circular prime or not
"""

Provide the list of circular prime numbers 


**Response**

Here’s a complete solution to find and validate all circular primes below 1 million.

✅ Expert Python:
python
Copy
Edit
from sympy import isprime

def get_rotations(n):

    """Generate all rotations of a number."""
    
    s = str(n)
    
    return [int(s[i:] + s[:i]) for i in range(len(s))]

def is_circular_prime(n):

    """Check if all rotations of a number are prime."""
    
    rotations = get_rotations(n)
    
    return all(isprime(rot) for rot in rotations)
    

def find_circular_primes(limit):

    """Find all circular primes below a given limit."""
    
    circular_primes = []
    
    for num in range(2, limit):
    
        if isprime(num) and is_circular_prime(num):
	
            circular_primes.append(num)
	    
    return circular_primes

# Get all circular primes below 1 million

circular_primes_below_1m = find_circular_primes(10**6)

print(f"FINAL: {circular_primes_below_1m}")

✅ Expert Mathematician:

Definition: A circular prime is a prime number where all rotations of its digits are also prime.

Validation Process:

Check if a number is prime.

Generate all possible rotations of the digits.

Verify if each rotation is also prime.

For example:

197 → 971 → 719, all are prime.

37 → 73 → both are prime.

The code correctly generates and validates circular primes by iterating through numbers below 1 million.

🔥 List of Circular Primes Below 1 Million:
yaml
Copy
Edit
FINAL: [2, 3, 5, 7, 11, 13, 17, 31, 37, 71, 73, 79, 97, 
113, 131, 197, 199, 311, 337, 373, 719, 733, 919, 971,
991, 1193, 1931, 3119, 3779, 7793, 7937, 9311, 9377,
11939, 19391, 19937, 37199, 39119, 71993, 91193, 
93719, 93911, 99371, 193939, 199933, 319993, 
331999, 391939, 393919, 919393, 933199, 939193,
939391, 993319, 999331]

✅ FINAL: 55 Circular Primes below 1 million.

---------------------------------------------------------------------------------------------------------

****Self Consistency Prompting****

****Approach tht simply asks model same chain of thought prompt multiple times and takes majority result as Final answer****

**Objective**

Find the age of sister comparing the age with her brother

**Prompt**

Q: Olivia has $23. She bought five bagels for $3 each. How much money does she have left?
A: She bought 5 bagels for $3 each. This means she spent $15. She has $8 left.
Q: When I was 6 my sister was half my age. Now I’m 70 how old is my sister?
A:

**Response 1**

When you were 6 years old, your sister was half your age, which means she was:

6
÷
2
=
3
 years old.
6÷2=3 years old.
The age difference between you and your sister is:

6
−
3
=
3
 years.
6−3=3 years.
Now that you are 70 years old, your sister is:

70
−
3
=
67
 years old.
70−3=67 years old.
✅ Final answer: Your sister is 67 years old. 🎉


**Response 2**

When you were 6 years old, your sister was half your age, which means she was:

6
−
3
=
3
 years old.
6−3=3 years old.
The age difference between you and your sister is 3 years.

Now that you are 70 years old, your sister is:

70
−
3
=
67
 years old.
70−3=67 years old.
✅ Final answer: Your sister is 67 years old. 🎉


**Response 3**

When you were 6 years old, your sister was half your age, meaning she was:

6
−
3
=
3
 years old.
6−3=3 years old.
The age difference between you and your sister is 3 years.

Now that you are 70 years old, your sister is:

70
−
3
=
67.
70−3=67.
✅ She has $67$ years left. 🎉


---------------------------------------------------------------------------------------------------------------------
