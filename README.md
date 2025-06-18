# Invoice Status Chatbot

A sophisticated chatbot solution for handling invoice status queries with natural language conversation capabilities. The system supports both PO and Non-PO invoice queries, with template-based data collection and integration with SAP S4 and ServiceNow systems.

## Features

- Natural language conversation for invoice status queries
- Support for both PO and Non-PO invoices
- Template-based data collection
- Integration with SAP S4 for invoice status
- ServiceNow ticket creation
- Multiple user types (Internal/External)
- Modern UI with React and Streamlit
- Robust error handling and validation
- Comprehensive logging and monitoring
- Type-safe implementation with Pydantic

## Architecture

The system is built using a modern microservices architecture:

- Frontend: React.js and Streamlit
- Backend: FastAPI
- Agent Framework: LangGraph
- Memory Management: LangMem and SAP HANA Cloud
- Monitoring: OpenTelemetry
- Testing: Pytest and DeepEval

## Prerequisites

- Python 3.9+
- Node.js 16+
- SAP HANA Cloud instance
- SAP S4 system access
- ServiceNow instance
- LLM API key (configurable provider)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/your-org/invoice-chatbot.git
cd invoice-chatbot
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
.\venv\Scripts\activate  # Windows
```

3. Install Python dependencies:
```bash
pip install -r requirements.txt
```

4. Install frontend dependencies:
```bash
cd frontend/react-app
npm install
```

5. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your configuration
```

## Configuration

The following environment variables need to be configured in `.env`:

```env
# API Configuration
API_HOST=0.0.0.0
API_PORT=8000

# Database
HANA_HOST=your-hana-host
HANA_PORT=443
HANA_USER=your-hana-user
HANA_PASSWORD=your-hana-password

# SAP S4
SAP_HOST=your-sap-host
SAP_CLIENT=your-sap-client
SAP_USER=your-sap-user
SAP_PASSWORD=your-sap-password

# ServiceNow
SNOW_INSTANCE=your-snow-instance
SNOW_USER=your-snow-user
SNOW_PASSWORD=your-snow-password

# LLM Configuration
LLM_PROVIDER=openai  # or other supported providers
LLM_API_KEY=your-llm-api-key

# Security
JWT_SECRET=your-jwt-secret
JWT_ALGORITHM=HS256
```

## Running the Application

1. Start the backend server:
```bash
cd backend
uvicorn app.main:app --reload
```

2. Start the React frontend:
```bash
cd frontend/react-app
npm start
```

3. Start the Streamlit frontend (alternative):
```bash
cd frontend/streamlit-app
streamlit run app.py
```

## Development

### Code Style

The project uses:
- Black for Python code formatting
- isort for import sorting
- mypy for type checking
- flake8 for linting

Run the pre-commit hooks:
```bash
pre-commit install
pre-commit run --all-files
```

### Testing

Run the test suite:
```bash
pytest
```

Run with coverage:
```bash
pytest --cov=app tests/
```

## Deployment

### Docker Deployment

1. Build the Docker images:
```bash
docker-compose build
```

2. Start the services:
```bash
docker-compose up -d
```

### Kubernetes Deployment

1. Apply the Kubernetes configurations:
```bash
kubectl apply -f k8s/
```

2. Monitor the deployment:
```bash
kubectl get pods
kubectl logs -f deployment/invoice-chatbot
```

## Monitoring

The application uses OpenTelemetry for monitoring. Access the metrics:

1. Prometheus metrics: `http://localhost:8000/metrics`
2. Grafana dashboard: `http://localhost:3000`

## API Documentation

Once the application is running, access the API documentation:

- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, please:
1. Check the [documentation](docs/)
2. Open an issue in the repository
3. Contact the development team

## Acknowledgments

- LangGraph for the agent framework
- FastAPI for the backend framework
- React and Streamlit for the frontend
- OpenTelemetry for monitoring
- SAP and ServiceNow for system integration 