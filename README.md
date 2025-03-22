    ******Prompting techniques******
    -----------------------------------
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
