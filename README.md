# ChatGPT Demo

Simple script to use ChatGPT on your own data or files.

## Installation

Install Python, if you haven't already (tested with v3.11).

Install [Langchain](https://github.com/hwchase17/langchain) and other required packages.
```
pip install langchain openai chromadb tiktoken unstructured unstructured[pdf]
```
Modify `constants.py.default` to use your own [OpenAI API key](https://platform.openai.com/account/api-keys), and rename it to `constants.py`.

Modify line 38 of chatgpt.py to switch different OpenAI models. For this demo, the code is set to use "gpt-4" model." gpt-4" model is better that "gpt-3.5". But, if you don't have access to "gpt-4" model, set model in line 38 to "gpt-3.5-turbo". 

Place your own data into `data/data.txt`.

## Example usage

Test reading `data/cat.pdf` file.
```
> python chatgpt.py "what is my cat's name"
Your cat's name is Muffy.
```
Test reading `data/employees.pdf` file.
```
> python chatgpt.py "List the employee names and their jobs at the demo.com and who is the top person?"
The full names of the leadership at the company are:

- Steven King (President)
- Neena Kochhar (Vice President)
- Lex De Haan (Vice President)

The top person at the company is Steven King, who holds the position of President.

> python chatgpt.py "Write a one parapgrah email body for each employee on the list. The tone and messaging must be fitting for the employee's title or position in the company."

TLDW - too long didn't write

```

Test reading `data/demo-financials.txt` file.
```
> python chatgpt.py "how would you describe demo.com's revenue performance, YOY"
The year-on-year revenue performance of demo.com shows a steady increase. In 2019, the total revenue was 24,578,000. This increased to 31,536,000 in 2020, and then further increased to 53,823,000 in 2021. The most significant rise was seen in 2022, where the revenue reached 81,462,000. Therefore, demo.com has been experiencing consistent growth in revenue year after year.
Prompt: what is demo.com's latest revenue
The latest revenue of demo.com is 81,462,000.
```

Test generating data using `data/demo-financials.txt`and `data/employees.pdf` files.
```
> python chatgpt.py "Write a one parapgrah email body for each employee on the list. The tone and messaging must be fitting for the employee's title or position in the company. If employee is the President, emphasize the need to beat demo.com revenue in 2023 (mention the dollar amount fron 2022 financials). If employee is not leadership, just congratulate them for job well done."

Certainly, I can help you draft the emails accordingly....
```

## Credits

[langchain base code] (https://github.com/techleadhd/chatgpt-retrieval)

[Example employees roster] (https://gist.github.com/kevin336/acbb2271e66c10a5b73aacf82ca82784)

[Example financial data ] (https://www.nasdaq.com/market-activity/stocks/tsla/financials)




