# Host-a-dynamic-website-on-EC2-and-AWS-cloudProject Overview

This project involved hosting Nest's dynamic web application on AWS using the LAMP stack. The deployment followed a reference architecture to ensure scalability, security, and reliability. The project was completed successfully, and the website was deployed on an Amazon EC2 instance with proper database integration and encryption.

Technologies Used

Cloud Provider: AWS

Compute: Amazon EC2 (Amazon Linux 2023 AMI)

Database: Amazon RDS (MySQL 8)

Storage: Amazon S3

Web Server: Apache

Backend: PHP 8 with required extensions

Deployment Tool: Flyway (for database migration)

Steps Completed

1. Hardware Setup

Launched an EC2 instance with Amazon Linux 2023 AMI.

Configured security groups to allow HTTP/HTTPS traffic.

2. Software Installation and Configuration

Installed Apache and PHP 8 with the required extensions:

sudo yum install -y httpd php php-cli php-fpm php-mysqlnd php-bcmath php-ctype php-fileinfo php-json php-mbstring php-openssl php-pdo php-gd php-tokenizer php-xml php-curl

Installed MySQL 8 and configured it for the database connection.

Modified php.ini settings:

memory_limit = 128M
max_execution_time = 300

Enabled Apache mod_rewrite module.

3. Application Deployment

Stored application code in an Amazon S3 bucket.

Migrated SQL script into Amazon RDS MySQL database using Flyway.

Copied application files from S3 to /var/www/html.

Set permissions for the application directory:

sudo chmod -R 777 /var/www/html
sudo chmod -R 777 /var/www/html/storage

Configured environment variables in .env:

APP_URL=your-domain.com
DB_HOST=your-rds-endpoint
DB_DATABASE=your-database-name
DB_USERNAME=your-username
DB_PASSWORD=your-password

Updated AppServiceProvider.php with the required boot function.

4. Security and Scaling

Configured SSL/TLS encryption for secure communication.

Set up an Auto Scaling Group to handle high traffic.

Implemented best practices for IAM roles and least privilege access.

Deliverables

URL of the fully deployed site: [Insert URL]

Screenshot of the encrypted site: [Insert Screenshot]

Screenshot of the Auto Scaling Group: [Insert Screenshot]

Conclusion

This project successfully deployed Nest's web application on AWS using a scalable and secure LAMP stack setup. The application is now live with database integration, SSL encryption, and an Auto Scaling Group for handling increased demand.


