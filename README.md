# Comandos EF Migrations

## Comando - Criar nova migração

cd ..
dotnet ef migrations add nome_da_migration -c "IContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Comando - Excluir ultima migração

cd ..
dotnet ef migrations remove -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Comando - Rodar no banco todas migrações pendentes

cd ..
dotnet ef database update -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Comando - Voltar para uma migração especifica

cd ..
dotnet ef database update "nome_migration" -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Combo - Reinserir migration que já está no banco

cd ..
dotnet ef database update "correcaoMigrations" -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef database update -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Combo - Refazer ultima migration que já está no banco

cd ..
dotnet ef database update "nome_migration" -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef migrations remove -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef migrations add nome_migration -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef database update -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Combo - Refazer ultima migration que não está no banco

cd ..
dotnet ef migrations remove -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef migrations add nome_migration -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef database update -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

## Combo - Criar uma nova migração e coloca-la no banco

cd ..
dotnet ef migrations add nome_migration -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
dotnet ef database update -c "ProjetoContext" -p "./Projeto.Data/Projeto.Data.csproj" -s "./Projeto.WebApi/Projeto.WebApi.csproj"
cd .\Projeto.WebApi\
dotnet run

