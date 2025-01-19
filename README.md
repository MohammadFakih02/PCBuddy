<img src="./readme/title1.svg"/>

<br><br>

<!-- project philosophy -->
<img src="./readme/title2.svg"/>

> An AI-powered website that helps users build custom PCs by recommending parts based on real-time pricing and performance needs.
>
> PCBuddy aims to make building custom PCs effortless by providing a platform that offers tailored part recommendations, assembly guidance, and performance insights. We believe in simplifying the PC-building process for enthusiasts and beginners alike by making it intuitive, informed, and accessible.

### User Stories
#### User
- I want to specify my budget and performance needs, so I can receive component recommendations that fit my requirements.
- I want to view how selected components perform in specific applications or games, so I can make informed decisions.
- I want to get guided assembly instructions, so I can confidently build my PC step-by-step.

#### Admin
- I want to view a list of all users using the app, so I can monitor their activity and manage their accounts.
- I want to view details of the systems built by users, so I can understand how the app is being used.
- I want to analyze statistics of the most used PC parts, so I can identify trends and popular components.

#### Technician
- I want to review and provide feedback on builds shared by regular users, so that I can help them optimize their configurations and ensure compatibility.
- I want to store and update a list of my clients and their builds,so that I can keep track of their system specifications and suggest upgrades or troubleshooting steps when needed.
- I want to mark specific builds as "For Sale" or "Available for Assembly," so that users looking for ready-made systems can purchase or request custom builds from me.

<br><br>
<!-- Tech stack -->
<img src="./readme/title3.svg"/>

###  PCBuddy is built using the following technologies:

- This project uses the [React.js](https://react.dev/) library for the frontend. React is a powerful JavaScript library for building user interfaces, enabling a dynamic and responsive user experience.
- For persistent storage (database), the app uses [PostgreSQL](https://www.postgresql.org/) a powerful open-source relational database system that allows the app to create a custom storage schema and save it to a scalable database.
- For the backend, the app is built using [Bun](https://bun.sh/) and [ElysiaJS](https://elysiajs.com/), which provide a fast and efficient server-side environment for handling API requests and business logic.
- The app uses the fonts Exo 2 and Lato as its main fonts, giving it a modern and professional typographic style. The design of the app adheres to the Material Design guidelines.


<br><br>
<!-- UI UX -->
<img src="./readme/title4.svg"/>


> We designed PCBuddy using wireframes and mockups, iterating on the design until we reached the ideal layout for easy navigation and a seamless user experience.

- Project Figma design [figma](https://www.figma.com/design/qz9PdCYoHBHLEpSRNtF5rh/PCBuddy?node-id=0-1&t=VoPEKotyFWKVcRa9-1)


### Mockups
| Home screen  | Recommendation Screen |
| ---| ---|
| ![Hero](./readme/images/Hero.png) | ![Form](./readme/images/Recommend_Form.png) |

<br><br>

<!-- Database Design -->
<img src="./readme/title5.svg"/>

###  Architecting Data Excellence: Innovative Database Design Strategies:

<img src="./readme/images/ERD.png"/>


<br><br>


<!-- Implementation -->
<img src="./readme/title6.svg"/>


### User Screens
| Register Sreen  | Login screen |
| ---| ---|
| ![Register](./readme/gifs/register.gif) | ![Login](./readme/gifs/login.gif) |
| Home screen  | Recommend Form |
| ![Landing](./readme/gifs/home.gif) | ![RecommendForm](./readme/gifs/recommendform.gif) |
| Recommend Results  | Build Form |
| ![Landing](./readme/gifs/recommendresults.gif) | ![RecommendForm](./readme/gifs/buildform.gif) |
| Build Results  | Benchmarks |
| ![Landing](./readme/gifs/buildresults.gif) | ![RecommendForm](./readme/gifs/benchmark.gif) |
| Build Guide  | Compare |
| ![Landing](./readme/gifs/buildguide.gif) | ![RecommendForm](./readme/gifs/compare.gif) |
| Laptop Assessment  | Profile |
| ![Landing](./readme/gifs/laptopassessment.gif) | ![RecommendForm](./readme/gifs/profile.gif) |

<br><br>


<!-- Prompt Engineering -->
<img src="./readme/title7.svg"/>

###  Mastering AI Interaction: Unveiling the Power of Prompt Engineering:

- This project uses advanced prompt engineering techniques to optimize the interaction with natural language processing models. By skillfully crafting input instructions, we tailor the behavior of the models to achieve precise and efficient language understanding and generation for various tasks and preferences.

   ```js
    Provide a detailed and step-by-step guide for assembling a PC with the following components:
    - CPU: ${cpu}
    - GPU: ${gpu}
    - RAM: ${ram}
    - Motherboard: ${motherboard}
    - PSU: ${psu}
    - Case: ${pcCase}

    Include:
    1. Step-by-step instructions with explicit details for each component's installation.
    2. A list of necessary tools for assembly.
    3. Cable management tips.
    4. Common pitfalls and precautions to avoid damage.
    5. Detailed explanations of terms and processes for beginners.

    Format the response as a JSON object with the following structure:
    {
      "tools": ["list", "of", "tools"],
      "steps": [
        {
          "title": "Step 1: Install the CPU",
          "description": [
            "1. Open the CPU socket lever on the motherboard.",
            "2. Carefully align the CPU's gold triangles with the corresponding markings on the socket.",
            "3. Gently lower the CPU into the socket.",
            "4. Close the lever securely.",
            "5. Do not force the CPU in; if it doesn't fit easily, double-check the alignment."
          ],
          "images": [],
          "imagePrompts": []
        },
        {
          "title": "Step 2: Install the CPU Cooler",
          "description": [
            "1. Apply a small pea-sized amount of thermal paste to the center of the CPU.",
            "2. Carefully align the cooler with the CPU and gently lower it into place.",
            "3. Secure the cooler using the provided mounting hardware."
          ],
          "images": [],
          "imagePrompts": []
        }
      ],
      "cableManagementTips": "Tips for managing cables...",
      "commonPitfalls": "Common mistakes to avoid..."
    }

    For each step, generate 2-3 search prompts that are specific to the topic but focus on the **action** being performed. The prompts should:
    - Describe the action (e.g., "installing a CPU," "connecting power cables").
    - Include contextual details about the step (e.g., "inside a PC case," "on a motherboard").
    - Use descriptive terms like "close-up," "step-by-step," or "diagram" to ensure the images are clear and relevant.
    - Avoid using overly specific component names (e.g., "Intel Core i7 CPU") unless absolutely necessary.

    Example prompts:
    - "Close-up of installing a CPU on a motherboard inside a PC case"
    - "Step-by-step diagram of installing RAM on a motherboard"
    - "Connecting power cables to a motherboard inside a PC case"

    Add these prompts to the "imagePrompts" field for each step.
    Ensure the response is valid JSON and does not contain any additional text or formatting outside the JSON object.
    ```

    ```js
        Given the following user prompt, return a JSON object with the best PC components that match the user's needs while strictly adhering to the budget and prioritizing high-performance CPU and GPU. IMPORTANT: Only use motherboards from the provided list below. Do not suggest motherboards that are not in this list.

    User Prompt: "${prompt}"

    Available Motherboards:
    ${availableParts.motherboards.map(m => m.name).join(", ")}

    The AI should:
    1. Stay strictly within the budget range provided by the user.
    2. Prioritize allocating the majority of the budget to the CPU and GPU to ensure high performance.
    3. Suggest components that are stronger or more capable than what the user requested, if possible within the budget.
    4. Suggest a PC build with the following components:
       - CPU name (prioritize high-performance models)
       - GPU name (prioritize high-performance models)
       - RAM name (do not include modules or speed)
       - PSU name (do not include efficiency)
       - Case name
       - HDD name (include capacity in GB)
       - SSD name (include capacity in GB)
       - Motherboard name (must be from the Available Motherboards list)

    Return the response in the following format:
    {
      "cpu": "name of the CPU",
      "gpu": "name of the GPU",
      "ram": "name of the RAM",
      "psu": "name of the PSU",
      "case": "name of the case",
      "hdd": "name of the HDD with capacity in GB",
      "ssd": "name of the SSD with capacity in GB",
      "motherboard": "name of the motherboard"
    }

    Ensure the response is a valid JSON object and does not contain any additional text or explanations.
    ```

<br><br>


<!-- How to run -->
<img src="./readme/title10.svg"/>

> To set up PCBuddy locally, follow these steps:

### Prerequisites

* npm
  ```sh
  npm install npm@latest -g
  ```
* bun
  ```sh
  powershell -c "irm bun.sh/install.ps1 | iex"
  ```
* [postegreSQL](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)
### Installation

_Below is an example of how you can instruct your audience on installing and setting up your app. This template doesn't rely on any external dependencies or services._

1. Get a free API Key at [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Get a free API key at [Google Custom Search JSON API](https://developers.google.com/custom-search/v1/overview)
   git clone [github](https://github.com/MohammadFakih02/PCBuddy)
3. Install NPM packages in PCBuddy-frontend
   ```sh
   npm install
   ```
4. Install Bun packages in PCBuddy-backend
   ```sh
   bun install
   ```
5. make a copy of your .env.example in the backend and name it .env, replace the placeholder with your own data
   ```js 
   DATABASE_URL="postgresql://postgres:yourpassword@localhost:5432/PCBuddy?schema=public"

   JWT_SECRET="supersecret"
   JWT_ACCESS_EXPIRES_IN="15m"
   JWT_REFRESH_EXPIRES_IN="7d"
   NODE_ENV="development"
   PORT=your_port
   BACKEND_URL=http://localhost:yourport
   GEMINI_API_KEY = "key"
   GOOGLE_CSE_ID = "ID"
   GOOGLE_API_KEY="key"
   ```
6. change the backend url in the api.js file in PCBuddy-frontend to match the one you have in the backend:
   ```js
   const API_BASE_URL = 'http://localhost:yourport';
   ```
7. npm start in PCBuddy-frontend
8. For the backend: Bun prisma migrate reset -> bun prisma:seed -> bun run dev

Now, you should be able to run PCBuddy locally and explore its features.
