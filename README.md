# attack-resistant-backup-recovery-showcase
 A showcase of my team's ARBR project and my specific contributions to the Backup &amp; Integrity Module.

Individual Contribution Summary:
My primary responsibility was designing and implementing the Backup Protection and Integrity module. This is a critical defense layer that ensures backups are verified and protected against ransomware tampering before any recovery process begins.

Specific Components I Built:

· Backup Manager (manager.py): Developed the core logic for creating backups, utilizing rsync for efficient file synchronization and shutil for cross-platform compatibility. I also implemented a lock_backup() function to make backup files immutable (read-only) to prevent ransomware encryption.
· Integrity Hashing (integrity.py): Wrote a cryptographic algorithm using SHA-256 to generate digital fingerprints for both individual files and entire directories. This ensures that if even a single byte of a backup is altered, the system detects it.
· Tamper Detection (verification.py): Implemented the verification logic that compares the stored hash of a backup against its current hash. If the hashes do not match, the backup is flagged as "UNTRUSTED" and blocked from recovery.
· API Integration (routes.py): Developed the REST API endpoints (/api/backup/create and /api/backup/backups/{id}/verify) to allow the React Dashboard to trigger backups and verify their integrity.
· Testing & Quality Assurance: Wrote and debugged the unit tests for the backup module. I successfully resolved merge conflicts, fixed import and indentation errors, and ensured all 50 backend tests passed prior to integration.


