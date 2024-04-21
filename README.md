# Migrating repositories between GitHub products

The GitHub CLI simplifies the migration process and is recommended for most customers. Advanced customers with heavy customization needs can use the API to build their own integrations with GitHub Enterprise Importer.

## Prerequisites

- To ensure you understand the known support limitations of the Importer, review "[About GitHub Enterprise Importer](https://docs.github.com/en/enterprise-cloud@latest/migrations/using-github-enterprise-importer/understanding-github-enterprise-importer/about-github-enterprise-importer#support-limitations-for-github-enterprise-importer)."
- Understand the requirements documented on [Managing access for a migration between GitHub products](https://docs.github.com/en/enterprise-cloud@latest/migrations/using-github-enterprise-importer/migrating-between-github-products/managing-access-for-a-migration-between-github-products#required-roles).
- We strongly recommend that you perform a trial run of your migration and complete your production migration soon after. To learn more about trial run best practices, see "[Preparing to run a migration with GitHub Enterprise Importer](https://docs.github.com/en/enterprise-cloud@latest/migrations/using-github-enterprise-importer/preparing-to-migrate-with-github-enterprise-importer/preparing-to-run-a-migration-with-github-enterprise-importer)."
- While not required, **we recommend halting work during your production migration**. The Importer doesn't support delta migrations, so any changes that happen during the migration will not migrate. If you choose not to halt work during your production migration, you'll need to manually migrate these changes.
- You must be either an organization owner or be granted the migrator role for both the source and destination organizations. For more information, see ["Granting the migrator role for GitHub Enterprise Importer."](https://docs.github.com/en/enterprise-cloud@latest/migrations/using-github-enterprise-importer/migrating-between-github-products/managing-access-for-a-migration-between-github-products#granting-the-migrator-role)

## Next steps

- Ensure your runner has been setup (e.g. with necessary tools)
- [**Self service setup**](./01.self-service-setup.md)
- [**Usage guide**](./02.usage.guide.md)