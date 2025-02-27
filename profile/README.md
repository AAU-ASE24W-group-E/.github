# Crowd Library - Book Management System (ASE WS2024)
Crowd Library is an web application for exchanging, lending and finding (physical) books in your area. It can be used by people who want to read books and / or by people who want to share their books with others
## Main Functionality
- Web Application
- Listing Books
- Finding Book Related Locations
- Find Books on Map
- Lending Books
- Tracking Lent Books
- Dark Mode
## Technology Stack
### Frontend
- Vue3 as core framework
- TailwindCSS for styling
- Vitest for unit testing
- Cypress for end-to-end testing
### Backend
- Quarkus as core framework
- Microservices
- PostGreSQL & PostGis
- Hibernate ORM wiht Panache
- OpenAPI
- Docker & Kubernetes
### CI/CD + GitOps
- CI: SonarCloud Analysis
- CD: Automatic build of container image publish to GitHub group container registry
- GitOps: k8s state is managed in Git repository & automatically updates state from Git
## Getting Started
To execute and run the application there are two possibilities:
1) **Cloning all GitHub Repositories and starting Backend and Frontend**
   - **Prerequisities**
     - npm & [nodejs](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
     - [Docker Desktop](https://www.docker.com/products/docker-desktop/)
   - Clone all relevant repositories:
     - cl-book-service
     - cl-lending-service
     - cl-user-service
     - crowd-library-web
   - Start Docker Desktop
   - Start the backend microservices (you can use IntelliJ build-in quarkus service starting feature)
     - **Hint:** Ensure that all used ports (8080, 8081, 8082) are free
   - Install dependencies in frontend using ``npm i``
   - Start the frontend using ``npm run dev``
   - Access webpage via ``http://localhost:5173/``
2) **Using Docker image published to GitHub group container registry**
   - **Prerequisities** 
     - **[Docker Desktop](https://www.docker.com/products/docker-desktop/)**
     - **[Minikube](https://minikube.sigs.k8s.io/docs/start/)** 
     - **[Kubernetes](https://kubernetes.io/releases/download/)**
   - Clone the repository **crowd-library**: ``git clone https://github.com/AAU-ASE24W-group-E/crowd-library.git``
   - Use a command line tool that can execute shell scripts
   - Check out into ``crowd-library/k8s/minikube``
   - Execute: ``./startminikube.sh``
   - Execute: ``./awaitstartup.sh``
   - Execute: ``./applystate.sh``
   - After executing all shell scripts and a successful start, you now have to create a tunnel using minikube to open the web application: ``minikube tunnel``
   - You should now be able to access the page using ``http://localhost``

## Web Page
Start your journey on our landing page
![Landing](/profile/assets/Screenshot_7.png)
All pages are also available in dark mode ;)
![Landing](/profile/assets/Screenshot_8.png)

After logging in, you can then search for books that are available at your location
![Landing](/profile/assets/Screenshot_2.png)
There is also a map where the books are stored
![Landing](/profile/assets/Screenshot_3.png)

Using our bookish map, you can search for all available book stores and filter the ones you want to see
![Landing](/profile/assets/Screenshot_4.png)

As seller, you can add books by ISBN that can be lent and see the books that are currently borrowed
![Landing](/profile/assets/Screenshot_1.png)

When a user requests a book from the books list, they can access an overview displaying both the books they have requested and the books requested by others from them
![Landing](/profile/assets/Screenshot_6.png)

...and many more features