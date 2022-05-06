1. Создание проекта

2. sequelize 
npm install --save sequelize
npm install --save mysql2 
npm install --save-dev sequelize-cli

3. Миграции
npx sequelize-cli model:generate --name Team --attributes name:string
npx sequelize-cli model:generate --name Player --attributes firstName:string,lastName:string,teamId:integer

4. Связь в миграции
   
      `teamId: {
      type: Sequelize.INTEGER,
      references: {
      model: {
      tableName: 'Teams',
      },
      key: 'id'
      },
      allowNull: false
      },`
5. Связь в модели
   `this.hasMany(models.Player, {foreignKey: 'teamId', as: 'Player'});`
6. Запуск миграции
   npx sequelize-cli db:migrate

7. Заполнили команды в БД
8. Вывели - изменили роут, и файл views
9. 