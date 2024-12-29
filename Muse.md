<img src="https://github.com/fuseai-fellowship/personal-museum-guide/blob/main/frontend/src/Logohorwhite.svg" height="250" width="1118">  

**MUSE** is an application designed to enhance the museum visit by providing conversational insights about artifacts, making it easy for users to learn more about exhibits in a natural and immersive way. It uses a **Multi-label Classification Model** to recognize museum exhibits and chat with users through the **Retrieval-Augmented Generation (RAG)** model using OpenAI API. In addition to this, it includes a **Text-to-Speech** feature to offer a more interactive and engaging experience.

## Objective/Scope
- Develop a conversation system capable of handling user queries related to museum exhibits.
- Build a model to recognize the exhibit from the image.
- Integrate speech for providing spoken responses to users.

## Contributors
- [Mamata Maharjan](https://github.com/Mavis021)
- [Aditi Kharel](https://github.com/aditikharel)
- [Aayusha Odari](https://github.com/ayusao)

## Project Architecture
The system consists of the following components:
1. **User Interface**  
   The system features a simple web application, providing a clean interface for users to interact with the virtual museum guide. Users can ask questions and receive information about exhibits through text input. The system responds with either text-based or voice responses depending on user preferences.

2. **Backend Services**  
   The backend services are responsible for processing user queries, generating appropriate responses, and ensuring smooth interaction. The main components include:


   - **Retrieval-Augmented Generation (RAG) Model:** Generates responses to user queries by combining retrieval of relevant text chunks from the museum knowledge base.
       
     <img src="https://github.com/fuseai-fellowship/personal-museum-guide/blob/main/docs/Assets/rag.png" height="273" width="395">  
   - **Multi-Label Image Classification:** This component assigns one or more labels to each artifact. Given a new image for an exhibit it predicts the labels for it.
               
     <img src="https://github.com/fuseai-fellowship/personal-museum-guide/blob/main/docs/Assets/modelarchflow.png" height="452" width="251">   
     <img src="https://github.com/fuseai-fellowship/personal-museum-guide/blob/main/docs/Assets/modelarch.png" height="252" width="600"> 
    
4. **Speech Processing**
For voice-based interactions, the system incorporates a Text-to-Speech(TTS) module that can provide spoken responses, by converting text answers into speech for users who prefer audio output.


# Status

## Known Issue
- Little to no support for conversations unrelated to museum exhibits
- Overfitting due to small dataset
- Single User System

## High Level Next Steps
- Expand the knowledge base with additional exhibit data
- Build a mobile app for real-time interaction through camera
- Integrate speech-to-text allowing voice commands

# Usage
Follow the steps below to use the application:

### 1. Clone the Repository
To get started, clone the repository to your local machine:
```bash
git clone https://github.com/fuseai-fellowship/personal-museum-guide.git
cd personal-museum-guide
```

### 2. Install Dependencies
Ensure all necessary Python, React frontend and flask backend dependencies are installed.

For Python:
```bash
pip install -r requirements.txt
```

### 3. Run the Application

#### React Frontend:
Navigate to the frontend directory and compile.
```bash
cd frontend
npm install
npm run build
```
#### Flask Backend:
To run the web app locally, use the following command:
```bash
cd ..
python app.py
```
The web interface will be accessible at `http://localhost:5000`.


<!-- #### pre-commit

`pre-commit` will automatically format and lint your code. You can install using this by using
`make use-pre-commit`. It will take effect on your next `git commit` -->
<!-- 
#### pip-tools

The method of managing dependencies in this package is using `pip-tools`. To begin, run `make use-pip-tools` to install. 

Then when adding a new package requirement, update the `requirements.in` file with 
the package name. You can include a specific version if desired but it is not necessary. 

To install and use the new dependency you can run `make deps-install` or equivalently `make`

If you have other packages installed in the environment that are no longer needed, you can you `make deps-sync` to ensure that your current development environment matches the `requirements` files.  -->

## Usage Instructions
- Upload an image of an exhibit to get predictions from the multi-label classification model.
- Ask questions about the exhibit to get responses from the RAG model.
- MUSE will speak the responses for a more immersive experience.

# Data Source
MUSE uses a JSON dataset for artifact descriptions that contains the details of the museum artifacts. Each entry includes the following fields:
- `id`: Unique identifier of the artifact.
- `name`: Name of the exhibit.
- `description`: A detailed description of the artifact.
- `origin`: The place and era of origin.
- `fun_fact`: Interesting facts about the exhibit.
- `type`: The type of artifact (sculpture, painting, etc.).
- `material`: The material used in the creation of the artifact.
- `technique`: The techniques used to create the artifact.

This dataset is located in the `/docs` folder within the backend and is used for retrieval when the RAG model processes queries.

## Code Structure

The repository is divided into two main components: the **frontend** (React) and the **backend** (Flask).

### src/personal-museum-guide/
- `src/personal-museum-guide`: Contains the main source codes for chatbot and a Multi-label classification model
- `src/personal-museum-guide/app.py`: The main Flask application.
- `src/personal-museum-guide/templates/`: Contains the HTML templates served by Flask.

### Frontend/
- `frontend/src/`: Contains the main source code for the frontend.
- `frontend/src/components/`: React components that make up the user interface.

### docs/
- `docs/`: Documentation and any additional reference files for the project.

### notebook/
- `notebook/`: Interactive Python Notebooks of the models.

# Results

### Metrics Used

- **Binary Cross-Entropy (BCE) Loss**: This metric is used to measure the performance of the multi-label classification model. Each label is treated independently, and BCE is calculated for each label.
- **Binary Accuracy**: Used to evaluate the accuracy of predictions for each label in the classification task. It measures the percentage of correctly predicted labels.

# Demo
Click the image below:  
[<img src="https://github.com/user-attachments/assets/165ceaab-b830-4c8f-b570-63a6d38eba15" height="400" width="700">  ](https://youtu.be/mObhz98m0iQ)
