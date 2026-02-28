pipeline {
 agent any
 
 stages {
 
 stage('Checkout') {
 steps {
 git branch: 'main', url: 'https://github.com/samidhaskale/nodeapp.git'
 }
 }
 
 stage('Install Dependencies') {
 steps {
 dir('nodeapp') {
 bat 'npm install'
 }
 }
 }
 
 stage('Run App') {
 steps {
 dir('nodeapp') {
 bat '''
 start /B node index.js
 timeout /t 5
 taskkill /IM node.exe /F
 '''
 }
 }
 }
 
 }
}
