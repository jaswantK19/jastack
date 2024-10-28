# Jastack.io

## This is my attempt at learning Deno and Astro by building my own portfolio + blogs website purely learning from documentation and not following entire tutorial.


- Tentative Diagram of how my project should look like:
```mermaid
flowchart TB
    subgraph Client["Frontend (Astro)"]
        direction TB
        Pages["Pages (Astro)"]
        Components["Components"]
        Assets["Assets"]
        MDX["Blog Posts (MDX)"]
        
        subgraph Static["Static Generation"]
            Portfolio["Portfolio Section"]
            Blog["Blog Section"]
            About["About Section"]
        end
    end

    subgraph Server["Backend (Deno)"]
        direction TB
        API["REST API"]
        Auth["Authentication"]
        
        subgraph Services["Services"]
            BlogService["Blog Service"]
            PortfolioService["Portfolio Service"]
            ImageService["Image Service"]
        end
        
        subgraph Data["Data Layer"]
            DB[(Database)]
            Assets_Storage["Asset Storage"]
        end
    end
    
    Client -- "API Calls" --> Server
    Pages --> Static
    MDX --> Blog
    Services --> Data
    API --> Services
```