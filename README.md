# AAI-540 Stellar Object Classification Tool

Production-oriented ML system for classifying SDSS objects into **star**, **galaxy**, or **quasar** using tabular photometric features.

**Team:** Group 7 — Alyona Kosobokova, Ian Rebmann  
**Project:** https://github.com/alonakos/aai-540-final-project

## Overview
This project builds an end-to-end multiclass classification pipeline using SDSS DR17-style data (~100k rows). The workflow includes preprocessing, feature engineering (color indices), model training (XGBoost), evaluation (macro-F1), batch inference, and basic production monitoring.

## Data
- Source: Stellar Classification Dataset (SDSS17)
- Features: u, g, r, i, z magnitudes, sky position, redshift
- Labels: STAR, GALAXY, QSO
- IDs and operational columns excluded from modeling

## Model
- Problem type: supervised multiclass classification  
- Primary metric: macro-F1  
- Baselines explored: CatBoost, LightGBM  
- Selected model: SageMaker XGBoost

## Pipeline
1. Validate schema and clean data  
2. Engineer color features (u−g, g−r, r−i, i−z)  
3. Train and evaluate models  
4. Store artifacts and metrics in S3  
5. Run batch inference (MVP)

## Monitoring
- Data quality: schema, missing values, feature ranges  
- Drift checks: magnitudes, redshift, class distribution  
- Model performance: macro-F1 and per-class recall  
- Operational metrics: job status and runtime

## Goal
Deliver a reproducible, deployment-ready ML system with clear monitoring and documentation for scientific use.

## Links
- Asana: https://app.asana.com/1/952672460738672/project/1212825865946195/board/1212826036922316  
- Team Tracker: https://docs.google.com/document/d/14sOXqJiOQrAZ4qY4rBN0UOZr0YqLy6sNRUPND_ztR4g/edit?usp=sharing
