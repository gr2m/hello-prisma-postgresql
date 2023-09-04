# hello-prisma

My Prisma test project, based on https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases-typescript-postgresql, with learnings from [open-sauced/api](https://github.com/open-sauced/api/tree/09f37a29d0f4b9606fc57efe471725fd9040baba#%EF%B8%8F-setting-up-a-postgresql-database-locally)

## Local development

See [dev/](dev/) to setup a local Postgress database.

Then copy `.env.example` to `.env`, no further edits should be necessary for local development.

```
cp .env.example .env
```

Then install dependencies

```
npm install
```

And start Prisma Studio, a browser UI for your postgress databse.

```
npm run prisma-studio
```

You can run the different `*.ts` scripts to experiment

```
npm run add-user
npm run list-users
npm run publish-post
```

## License

[ISC](license.md)
