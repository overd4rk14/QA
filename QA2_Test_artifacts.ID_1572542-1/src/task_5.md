Ресурсы для генерации файлов определенного размера:
1. https://file.generator.teremokgames.com
2. https://www.convertiom.com/file-generator.html
Ресурсы для генерации тестовых данных:
1. https://generatedata.com
2. http://www.randat.com

Воспользовался 1-ым сервисом для генерации файлов определенного размера.
Позитивные тесты для проверки функционала загрузки аватара с лимитом 5 МБ:
![аватар размером 4МБ](misc/images/avatar.png)
![аватар размером 2МБ](misc/images/avatar1.png)
Негативный тест для проверки функционала загрузки аватара с лимитом 5 МБ:
![аватар размером 7МБ](misc/images/avatar2.png)
![отображение в папке](misc/images/filesize.png)
5 тестовых пользователей, у которых будут данные (ФИО, номер телефона, email, адрес) для конкретной страны - Франция:
Номера во Франции состоят из 10 цифр, начиная с 0, и обычно указываются в формате: 0X XX XX XX XX.
![Онлайн-генерация данных](misc/images/datagen.png)
Результаты сформировались в JSON-файл (воспользовался 1-ым сервисом):
[
	{
		"name": "Phelan Anthony",
		"phone": "08 85 80 60 14",
		"email": "elit.erat@yahoo.ca",
		"address": "914-3147 Aliquet Avenue",
		"region": "Centre",
		"country": "France"
	},
	{
		"name": "Neville Davenport",
		"phone": "03 14 33 83 41",
		"email": "fusce.fermentum@outlook.net",
		"address": "183-2673 Gravida Road",
		"region": "Corse",
		"country": "France"
	},
	{
		"name": "Eaton Branch",
		"phone": "05 37 36 90 62",
		"email": "quisque.fringilla@icloud.org",
		"address": "607-6199 Libero. Ave",
		"region": "Provence-Alpes-Côte d'Azur",
		"country": "France"
	},
	{
		"name": "Kieran Strickland",
		"phone": "07 37 37 68 37",
		"email": "cursus.nunc@protonmail.couk",
		"address": "Ap #184-7771 Id, St.",
		"region": "Provence-Alpes-Côte d'Azur",
		"country": "France"
	},
	{
		"name": "Wyatt Ward",
		"phone": "05 68 17 22 80",
		"email": "nulla.in@icloud.edu",
		"address": "1234 Litora St.",
		"region": "Champagne-Ardenne",
		"country": "France"
	}
]