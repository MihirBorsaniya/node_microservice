
ecommerce-backend/
├── shared/                                       # Shared utilities and configurations
│   ├── db/                                       # Shared database connection for global data
│   │   ├── sequelize.js                          # Sequelize instance for shared DB
│   │   └── migrations/                           # Sequelize migrations for shared DB
│   │       ├── 20250508_create_users_table.js
│   │       ├── 20250508_create_themes_table.js
│   │       └── 20250508_create_store_databases_table.js
│   ├── middleware/                               # Shared middleware
│   │   ├── auth.js                               # JWT authentication middleware
│   │   └── errorHandler.js                       # Centralized error handling
│   └── utils/                                    # Utility functions
│       ├── logger.js                             # Logger for debugging
│       └── apiClient.js                          # HTTP client for inter-service communication
├── auth-service/                                 # Microservice for authentication (shared DB)
│   ├── config/                                   # Database config
│   │   └── db.js                                 # Sequelize instance for shared DB
│   ├── controllers/
│   │   └── authController.js
│   ├── routes/
│   │   └── authRoutes.js
│   ├── models/
│   │   └── User.js                               # Sequelize User model
│   ├── .env
│   ├── package.json
│   └── server.js
├── store-service/                                # Microservice for store management (dynamic DB)
│   ├── config/
│   │   └── db.js                                 # Dynamic Sequelize instances for stores
│   ├── controllers/
│   │   └── storeController.js
│   ├── routes/
│   │   └── storeRoutes.js
│   ├── models/
│   │   ├── Store.js                              # Sequelize Store model
│   │   └── Product.js                            # Sequelize Product model
│   ├── .env
│   ├── package.json
│   └── server.js
├── theme-service/                                # Microservice for theme management (shared DB)
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── themeController.js
│   ├── routes/
│   │   └── themeRoutes.js
│   ├── models/
│   │   └── Theme.js                              # Sequelize Theme model
│   ├── .env
│   ├── package.json
│   └── server.js
├── admin-service/                                # Microservice for store owner admin panels (dynamic DB)
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── adminController.js
│   ├── routes/
│   │   └── adminRoutes.js
│   ├── models/
│   │   └── Store.js                              # Reuses Store model
│   ├── .env
│   ├── package.json
│   └── server.js
├── super-admin-service/                          # Microservice for super admin panel (shared DB)
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── superAdminController.js
│   ├── routes/
│   │   └── superAdminRoutes.js
│   ├── models/
│   │   └── User.js                               # Reuses User model
│   ├── .env
│   ├── package.json
│   └── server.js
├── gateway/                                      # API Gateway for routing
│   ├── routes/
│   │   └── gatewayRoutes.js
│   ├── .env
│   ├── package.json
│   └── server.js
├── docker-compose.yml                            # Docker setup for services and DB
├── package.json                                # Root-level dependencies
└── README.md                                   # Project documentation