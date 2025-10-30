provider "aws" {
  access_key = ""
  secret_key = ""
  region     = "us-east-1"
}

resource "aws_instance" "chandutre" {
  ami           = ""
  instance_type = "t3.micro"
}
