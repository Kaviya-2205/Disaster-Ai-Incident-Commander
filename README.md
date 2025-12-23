# Mumbai Incident Commander 🚨

A real-time AI-powered emergency incident management system that processes multiple data sources, analyzes threats using AWS services, and provides actionable intelligence for emergency response teams.

## 🎯 Features

- **Multi-source Data Processing**: Handles CSV, JSON, PDF, and image files
- **AWS Integration**: Uses S3 for storage, Lambda for processing, and Bedrock for AI analysis
- **Real-time Analysis**: Processes emergency calls, distress messages, and sensor data
- **Risk Assessment**: AI-powered incident prioritization and confidence scoring
- **Interactive Dashboard**: Beautiful military-style UI with real-time visualizations
- **Action Planning**: Automated resource allocation and response recommendations

## 🏗️ Architecture

```
Frontend (HTML/JS) → Flask Backend → AWS S3 → AWS Lambda → AWS Bedrock → Results
```

1. **Frontend**: Upload interface and dashboard
2. **Flask Backend**: API server and file handling
3. **AWS S3**: Data storage and file management
4. **AWS Lambda**: Data processing and normalization
5. **AWS Bedrock**: AI analysis and insights
6. **Results Loop**: Processed data back to frontend

## 🚀 Quick Start

### Option 1: Automated Setup (Recommended)

```bash
# Clone or download the project
# Run the automated setup
python quick-deploy.py
```

This will:
- Set up all AWS resources (S3, Lambda, IAM)
- Configure environment variables
- Deploy the system automatically

### Option 2: Manual Setup

1. **Install Requirements**
```bash
pip install -r backend/requirements.txt
```

2. **Configure AWS Credentials**
```bash
cp backend/.env.example backend/.env
# Edit backend/.env with your AWS credentials
```

3. **Deploy AWS Infrastructure**
```bash
python aws-setup/deploy.py
```

4. **Start Backend**
```bash
python backend/app.py
```

5. **Open Frontend**
Open `http://localhost:5000` in your browser

## 📊 Dataset Format

The system processes these data types:

### Emergency Calls (CSV)
```csv
call_id,caller_type,issue_reported,location,call_duration_sec,timestamp
1,Police,Fire outbreak,Ghatkopar,300,2025-12-21 15:35:46
```

### Distress Messages (JSON)
```json
[
  {
    "id": 1,
    "message": "Building collapse hua hai",
    "location": "Malad",
    "timestamp": "2025-12-21 07:44:58"
  }
]
```

### Infrastructure Data (CSV)
```csv
name,type,capacity,status
Ghatkopar Hospital,Hospital,200,Operational
```

## 🔧 Configuration

### Environment Variables (.env)
```bash
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
AWS_REGION=ap-south-1
S3_BUCKET=mumbai-incident-data
```

### AWS Resources Required
- **S3 Bucket**: Data storage
- **Lambda Function**: Data processing
- **IAM Role**: Permissions
- **Bedrock Access**: AI analysis (optional)

## 🧪 Testing

Run the system test:
```bash
python test-system.py
```

This will verify:
- Backend API connectivity
- File upload functionality
- AWS integration
- Frontend accessibility

## 📱 Usage

1. **Upload Data**: Drag and drop CSV/JSON files on the home page
2. **AI Processing**: System automatically processes and analyzes data
3. **View Results**: Priority dashboard shows risk-ranked incidents
4. **Action Plans**: Click incidents to see detailed response plans
5. **Accept/Reject**: Approve or modify AI recommendations

## 🎨 Frontend Pages

- **Home** (`/`): File upload and data ingestion
- **Priority** (`/priority`): Risk dashboard and incident ranking
- **Action** (`/action`): Detailed response plans and resources

## 🔒 Security

- AWS IAM roles with minimal required permissions
- CORS configured for local development
- Environment variables for sensitive data
- S3 bucket versioning enabled

## 🛠️ Development

### Project Structure
```
├── frontend/           # HTML/CSS/JS files
├── backend/           # Flask application
├── datasets/          # Sample data files
├── aws-setup/         # AWS deployment scripts
├── quick-deploy.py    # Automated setup
├── test-system.py     # System testing
└── README.md         # This file
```

### Adding New Data Sources

1. Update `lambda_function.py` to handle new file types
2. Add processing logic in `analyze_incidents()`
3. Update frontend to accept new file formats

### Customizing AI Analysis

Modify the Bedrock prompt in `generate_ai_analysis()` to change AI behavior.

## 🚨 Troubleshooting

### Common Issues

**Backend won't start**
- Check Python version (3.8+ required)
- Install requirements: `pip install -r backend/requirements.txt`
- Verify .env file exists with AWS credentials

**AWS deployment fails**
- Verify AWS credentials have sufficient permissions
- Check AWS region supports required services
- Ensure unique S3 bucket name

**File upload fails**
- Check AWS Lambda function is deployed
- Verify S3 bucket permissions
- Check file size limits (Lambda has 6MB limit)

**No incidents detected**
- Verify data format matches expected schema
- Check Lambda logs in AWS CloudWatch
- Ensure data contains recognizable incident keywords

### Debug Mode

Enable debug logging:
```bash
export FLASK_DEBUG=True
python backend/app.py
```

## 📈 Performance

- **File Processing**: Up to 100MB per upload
- **Response Time**: 2-5 seconds for typical datasets
- **Concurrent Users**: Supports multiple simultaneous uploads
- **AWS Costs**: Minimal for development/testing

## 🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Add tests for new functionality
4. Submit pull request

## 📄 License

This project is for educational and emergency management purposes.

## 🆘 Support

For issues or questions:
1. Check troubleshooting section
2. Run `python test-system.py` for diagnostics
3. Check AWS CloudWatch logs for Lambda errors

---

**Built for Mumbai Emergency Response** 🏙️
*Powered by AWS AI Services* ☁️
