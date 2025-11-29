# Expat Tax Advisor RAG Monorepo
## Multi-Jurisdiction LLM Application for US Expats

## Project Structure: expat-tax-advisor-rag Monorepo
# This project uses a Monorepo structure to house multiple components of the RAG application, allowing for centralized configuration, shared code, and streamlined deployment.

# Folder/Path	Description	Purpose
**apps/**	        
Applications - Contains the independent, deployable services and clients:

**├── api/**	    - The FastAPI RAG API service, which handles inference requests, uses the shared rag_core package, and runs on Cloud Run.

**└── client/**	    - Frontend applications, such as the country-s

**packages/**	    
Shared Libraries - Contains internal, reusable code that can be imported by any application in the apps/ directory.

**└── rag_core/**	- The core Python library for the RAG system, including all common utilities for text chunking, embeddings, Gemini prompt wrappers, and Vector Store interaction.

**infra/**	      
Infrastructure as Code (IaC) - Stores all configuration files for defining and managing cloud infrastructure.

**└── gcp/**	    - Contains the Terraform configuration files (main.tf, variables.tf, etc.) used to provision the entire GCP environment (Project, Cloud Run, Vertex AI, GCS).

**docs/**	        
Documentation and Data Configuration - Houses human-readable documentation and configuration files for data pipelines.

**└── registry/**	- Stores the Content Manifests (e.g., YAML or CSV files) that list all source documents and metadata for the RAG data ingestion pipeline.

**.github/**	    
CI/CD - Contains configuration for GitHub Actions workflows.

**└── workflows/**	- Definitions for Continuous Integration / Continuous Delivery (CI/CD) pipelines, which automatically build, test, and deploy the application and infrastructure.