## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.


### DESIGN STEPS:
#### STEP 1:
Import the required libraries and load the API key.

#### STEP 2:
Create a prompt with 2 prompt parameters and initialize the model and output parser.

#### STEP 3:
Connect the components using the LCEL pipe operator (|) and execute the chain.

### PROGRAM:
```

import os
import openai

from dotenv import load_dotenv, find_dotenv

# Load environment variables
_ = load_dotenv(find_dotenv())
openai.api_key = os.environ["OPENAI_API_KEY"]

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

# STEP 1: Create prompt template
prompt = ChatPromptTemplate.from_template(
    "Explain {topic} in a short and simple way for {audience}"
)

# STEP 2: Initialize the model
model = ChatOpenAI(
    model="gpt-4o-mini",
    temperature=0.7
)

# STEP 3: Initialize output parser
output_parser = StrOutputParser()

# STEP 4: Connect components
chain = prompt | model | output_parser

# STEP 5: Execute the chain
response = chain.invoke({
    "topic": "Artificial Intelligence",
    "audience": "College students"
})

# STEP 6: Display output
print("Name: Sanjai T")
print("Reg no : 212224240144")
print("Generated Response:")
print(response)
```

### OUTPUT:
<img width="1212" height="282" alt="image" src="https://github.com/user-attachments/assets/133ad348-b290-4f2d-9d62-eba7255c911f" />


### RESULT:
Thus, the LCEL expression was successfully implemented. The chain generated meaningful responses and demonstrated its applications in real-world scenarios.
