# AIML-UC-Berkeley-Generative-AI

**In this project, using Generative AI, we produce text and image. Moreover, we can train image and improve its efficiency**

**We check the relative performance of different API with following prompts:**

**Instructional prompts** provide clear and specific instructions for the AI model to follow. ▪ Example: “Write a brief summary of the effect of global warming on health care.”

**Descriptive prompts** provide a description or context for AI to generate content based on. ▪ Example: “Briefly describe the steps required for addressing the effect of global warming on health care.”

**Question prompts** provide questions for AI to answer. ▪ Example: “What are the effects of global warming on health care?”

**Completion prompts** provide a partial question for AI to complete. ▪ Example: “The effect of global warming on health care can be addressed by the following steps…”

**Example-based prompts** provide an example for the type of output desired. ▪ Example: “One example of preventing effects of global warming on health care is to ‘Monitor emerging and re-emerging diseases that may be influenced by changing climate conditions.’ Provide more example on these grounds to reduce the effect of global warming on health care.”

**Here is an example:**
completion = client.chat.completions.create(
  model="gpt-4o-mini",
  store=True,
  messages=[
    {"role": "user", "content": "write a brief summary about the effects of high inflation on economy "}
  ]
)
#print(completion.choices[0].message);
#Extract and format the response:
narrative = completion.choices[0].message.content
#formatting
narrative.replace('\n', ' ')

### Analyze Effectiveness for Prompt Instructional:

### Relevance:

The response address the prompt completely and correctly, and then it has high level of relevance.

### Coherence:

Response has logical structure and easy to understand. For someone who has knowledge in economics, this answer is very direct and easy to understand. Therefore, it has high level of coherence.

### Creativity:

This answer covers various dimensions of the effect on economy. At first focused on purchase power, then to uncertainty, then to income and stability. Then it has high level of creativity too.

### Accuracy:

Information provided are correct, and then its accuracy is high too.

### **Huging Face**
**We also use hugging face and analyze a dataset to get description and prediction**
### Example: 
chat_completion = client.chat.completions.create(
    messages=[
        {"role": "user", "content":  f"Analyze the average sales for the top 10 cities: {data_dict['data']}"}
    ],
    model="gpt-3.5-turbo",
)

narrative = chat_completion.choices[0].message.content

narrative.replace('\n', ' ')
     
"To analyze the average sales for the top 10 cities, we need to first extract the sales data for each city from the given list. Then, we can calculate the average sales for each city and finally determine the average sales for the top 10 cities.  Here are the sales data for the top 10 cities: 1. City 1: 25.5000 2. City 2: 2729.9860 3. City 3: 5519.5700 4. City 4: 3773.0628 5. City 5: 20214.5320 6. City 6: 17197.8400 7. City 7: 11656.4780 8. City 8: 9063.4960 9. City 9: 7452.9960 10. City 10: 64504.7604  Now, let's calculate the average sales for the top 10 cities:  Total sales = 25.5000 + 2729.9860 + 5519.5700 + 3773.0628 + 20214.5320 + 17197.8400 + 11656.4780 + 9063.4960 + 7452.9960 + 64504.7604 = 144538.2212  Average sales = Total sales / Number of cities Average sales = 144538.2212 / 10 = 14453.82212  Therefore, the average sales for the top 10 cities is $14,453.82."


### Practice Fine-Tuning Diffusion Models


## Generating the Text Narrative from Your Data
using a dataset that contains list of video games with global sales greater than 100,000 copies. The fields in this dataset include:

Rank: The ranking of overall sales

Name: The name of the video game

Platform: The platform of the games release (i.e. PC,PS4, etc.)

Year: The year of the game's release

Genre: The genre of the game

Publisher: The publisher of the game

NA_Sales: Sales in North America (in millions)

EU_Sales: Sales in Europe (in millions)

JP_Sales: Sales in Japan (in millions)

Other_Sales: Sales in the rest of the world (in millions)

Global_Sales: Total worldwide sales.


