# Amazon S3 Storage Lab

This lab documents the review and secure configuration of an existing Amazon S3 bucket
to align with AWS best practices for security, durability, and cost awareness.

---

## Objectives

- Review an existing S3 bucket configuration
- Validate and enforce secure defaults
- Enable versioning and encryption
- Confirm private access behavior
- Understand lifecycle and cost optimization concepts

---

## Bucket Details

- Bucket name: nicky-cloud-portfolio-2025-use1
- Region: us-east-1
- Bucket purpose: Portfolio artifacts and learning labs

---

## Configuration Review

The following settings were validated and updated as needed:

- Public access: Blocked at bucket level
- Versioning: Enabled
- Default encryption: SSE-S3

---

## Security Considerations

- All public access is blocked
- Objects encrypted at rest by default
- No public bucket policies or ACLs applied
- Access managed via IAM permissions

---

## Versioning Validation

- Multiple versions of the same object uploaded
- Verified ability to view object versions
- Confirms protection against accidental deletion or overwrite

---

## Access Testing

- Direct object URL access tested
- Access denied response confirmed
- Validates private bucket configuration

---

## Cost Awareness

- Bucket usage kept within AWS Free Tier limits
- Lifecycle policies reviewed conceptually
- Storage reviewed after lab completion

---

## Key Takeaways

- Existing cloud resources should be reviewed and hardened regularly
- Secure defaults are essential to prevent data exposure
- Versioning and encryption are baseline production requirements
- Cost management applies even to foundational services like S3
