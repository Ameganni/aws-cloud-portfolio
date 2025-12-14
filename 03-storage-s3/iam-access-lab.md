# S3 and IAM Access Control Lab

This lab demonstrates the implementation, validation, and troubleshooting of
least privilege IAM access to an Amazon S3 bucket.

The objective was to grant a limited user read only access to a specific S3 bucket
while preventing all write, delete, and administrative actions.

---

## Objectives

- Create a custom IAM policy with least privilege access
- Grant read only access to a single S3 bucket
- Validate allowed and denied actions
- Understand AWS console visibility behavior
- Practice real world troubleshooting and root cause analysis

---

## Environment Overview

- AWS Region: us east 1
- S3 Bucket: nicky cloud portfolio 2025 use1
- Bucket status: Active and reused for future labs
- IAM principal type: IAM user

---

## IAM User Configuration

A dedicated IAM user was created for access testing.

- User name: s3 read only user
- Access type: AWS Management Console
- Permissions model: Custom IAM policy
- Intended access scope: Single S3 bucket read only

The root user was not used for testing.

---

## IAM Policy Design

A custom IAM policy was created to allow the following actions:

Allowed:
- View S3 bucket list at the account level
- List objects within the target bucket
- Read objects from the target bucket

Not allowed:
- Upload objects
- Delete objects
- Modify bucket settings
- Access other buckets

The policy followed the principle of least privilege and scoped permissions to
only the required resources.

---

## Access Validation

### Allowed Actions

- View bucket name in the S3 console
- Open the target bucket
- List objects within the bucket
- Download objects

### Denied Actions

- Upload new objects
- Delete existing objects
- Modify bucket configuration
- Access other S3 buckets

Access denied responses were confirmed for restricted actions.

---

## Console Visibility and Troubleshooting

During testing, the bucket initially appeared empty when accessed by the read only user.

This behavior was investigated and correctly identified as a data state issue rather
than a permissions issue, as all objects had been deleted during earlier cleanup.

After uploading a new object using an administrative account, the read only user
was able to list and download objects as expected.

This reinforced the importance of validating resource state before assuming
permission misconfiguration.

---

## Security Takeaways

- Least privilege access reduces security risk
- Custom IAM policies provide precise control
- AWS console behavior may require additional read permissions
- Troubleshooting should distinguish between access issues and resource state
- Access should always be tested, not assumed

---

## Cost and Operational Awareness

- No additional AWS costs were incurred
- Existing resources were reused intentionally
- Permissions were scoped to avoid accidental changes
- Lab artifacts were retained for future integrations

---

## Future Enhancements

Planned improvements include:
- Enabling MFA for IAM users
- Replacing IAM users with IAM roles
- Testing access using AWS CLI
- Reviewing CloudTrail logs for access events
- Integrating the bucket with serverless workflows

---

## Key Outcome

This lab demonstrates practical IAM access control, security awareness,
and real world troubleshooting skills expected of a cloud engineer.
