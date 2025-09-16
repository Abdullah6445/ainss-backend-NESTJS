1) create nestJs project
(npx @nesjs/cli new project_name)

2) start the nest js project
(yarn start:dev)

3) install prisma cli
(yarn add -D prisma)

4) initialize prisma in project
(yarn prisma init)

5) initialize swagger in project
(yarn add @nestjs/swagger swagger-ui-express)

6) add DocumentBuiler in main.ts for prisma integration

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.enableCors();
  const config = new DocumentBuilder()
    .setTitle('Abdullah Swaggers')
    .setDescription('Building ServerSide Application With NestJS')
    .setVersion('0.1')
    .build();

  const document = SwaggerModule.createDocument(app, config);
  SwaggerModule.setup('swaggers', app, document);
  await app.listen(process.env.PORT ?? 3000);
}
bootstrap();

7) add prisma client in the project
(yarn add @prisma/client)

8) generate a module with controllers and service
(nest generate resource) command

9) add the model in the prisma.schema and run command (yarn prisma generate)

10) run the docker with (docker compose up -d) 

11) migrate the database with (yarn prisma migrate dev) command

12) migrate only the changes in database with (yarn prisma migrate deploy) command





yarn add nestjs-command
npx ts-node prisma/seed.ts
yarn add class-validator class-transformer
yarn add bcrypt

docker compose up -d
docker compose down