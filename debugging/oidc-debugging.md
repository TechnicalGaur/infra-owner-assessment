# OIDC Debugging Report

## Issue
After enabling OIDC, the Open WebUI pod entered CrashLoopBackOff state.

## Investigation
- Checked pod status using `kubectl get pods`
- Retrieved logs using `kubectl logs`
- Observed TLS error: certificate signed by unknown authority

## Root Cause
OIDC provider uses a self-signed certificate which is not trusted by the container trust store.

## Fix
Enabled `insecureSkipVerify` in Helm values to bypass certificate verification.

## Why It Works
Disables strict TLS verification allowing the application to communicate with the OIDC provider.

## Production Recommendation
- Mount custom CA certificate via ConfigMap
- Update container trust store
- Avoid disabling TLS verification in production
