# Project Structure

```
invoice-chatbot/
├── frontend/
│   ├── react-app/
│   │   ├── src/
│   │   │   ├── components/
│   │   │   ├── pages/
│   │   │   ├── services/
│   │   │   ├── utils/
│   │   │   └── App.tsx
│   │   ├── package.json
│   │   └── tsconfig.json
│   └── streamlit-app/
│       ├── pages/
│       ├── components/
│       └── app.py
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── core/
│   │   ├── models/
│   │   ├── services/
│   │   └── utils/
│   ├── tests/
│   │   ├── unit/
│   │   └── integration/
│   ├── alembic/
│   └── main.py
├── agent/
│   ├── agents/
│   │   ├── invoice_agent.py
│   │   └── tools/
│   ├── memory/
│   │   ├── short_term.py
│   │   └── long_term.py
│   └── prompts/
│       ├── system_prompts.py
│       └── user_prompts.py
├── config/
│   ├── settings.py
│   └── logging.py
├── docs/
│   ├── functional_spec.md
│   └── technical_spec.md
├── scripts/
│   ├── setup.sh
│   └── deploy.sh
├── .env.example
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
└── README.md
```

## Key Files Description

### Frontend
- `react-app/src/components/`: React components for UI
- `react-app/src/services/`: API integration services
- `streamlit-app/app.py`: Main Streamlit application

### Backend
- `app/api/`: FastAPI route handlers
- `app/core/`: Core business logic
- `app/models/`: Pydantic models
- `app/services/`: External service integrations
- `tests/`: Unit and integration tests

### Agent
- `agents/invoice_agent.py`: Main agent implementation
- `agents/tools/`: Custom tools for the agent
- `memory/`: Memory management implementations
- `prompts/`: System and user prompts

### Configuration
- `config/settings.py`: Application settings
- `config/logging.py`: Logging configuration

### Documentation
- `docs/functional_spec.md`: Functional specification
- `docs/technical_spec.md`: Technical specification

### Deployment
- `scripts/setup.sh`: Setup script
- `scripts/deploy.sh`: Deployment script
- `docker-compose.yml`: Docker compose configuration
- `Dockerfile`: Docker configuration 