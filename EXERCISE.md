# Ex query con select


## Request:

1. Selezionare tutti gli studenti nati nel 1990 (160)
2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
3. Selezionare tutti gli studenti che hanno più di 30 anni
4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)
5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)
6. Selezionare tutti i corsi di laurea magistrale (38)
7. Da quanti dipartimenti è composta l'università? (12)
8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

## Steps:

- Use comand C:\MAMP\bin\mysql\bin\mysql -u root -p to start the shell and enter in phpMyAdmin.
- Use show datatabses comand for look the databases. COMAND:(show databases;)
+--------------------+
| Database           |
+--------------------+
| information_schema |
| db_university      |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

- Use use comand to enter the selected database. COMAND:(USE `db_university`;)
- Use show tables comand to look the table inside the selected database. COMAND:(show tables;)
+-------------------------+
| Tables_in_db_university |
+-------------------------+
| course_teacher          |
| courses                 |
| degrees                 |
| departments             |
| exam_student            |
| exams                   |
| students                |
| teachers                |
+-------------------------+
8 rows in set (0.00 sec)

- Use describe comand to look over a selected row. COMAND:(describe "row_name")

1. Selezionare tutti gli studenti nati nel 1990 (160) :
mysql> SELECT `name`   
    -> FROM `students`
    -> WHERE `date_of_birth`
    -> LIKE '1990%';   
+--------------+
| name         |
+--------------+
| Lauro        |
| Matilde      |
| Marieva      |
| Marco        |
| Maika        |
| Fabiano      |
| Amedeo       |
| Tolomeo      |
| Eriberto     |
| Harry        |
| Ursula       |
| Pietro       |
| Harry        |
| Marino       |
| Cira         |
| Damiana      |
| Elda         |
| Maika        |
| Augusto      |
| Cira         |
| Boris        |
| Marcella     |
| Boris        |
| Egisto       |
| Laura        |
| Prisca       |
| Samira       |
| Flaviana     |
| Secondo      |
| Oreste       |
| Kociss       |
| Albino       |
| Mirko        |
| Tancredi     |
| Enrica       |
| Gianmarco    |
| Miriana      |
| Rodolfo      |
| Iacopo       |
| Cosetta      |
| Artemide     |
| Nayade       |
| Ethan        |
| Davis        |
| Olimpia      |
| Brigitta     |
| Laura        |
| Ruth         |
| Selvaggia    |
| Nazzareno    |
| Lucia        |
| Furio        |
| Carlo        |
| Tolomeo      |
| Raniero      |
| Danthon      |
| Erminia      |
| Giacinta     |
| Ortensia     |
| Costanzo     |
| Elio         |
| Ubaldo       |
| Rufo         |
| Rosalino     |
| Violante     |
| Samira       |
| Morgana      |
| Rudy         |
| Germano      |
| Elga         |
| Kristel      |
| Vania        |
| Rita         |
| Samira       |
| Manuele      |
| Donatella    |
| Folco        |
| Iacopo       |
| Pablo        |
| Cleros       |
| Silverio     |
| Damiana      |
| Primo        |
| Dindo        |
| Amos         |
| Monia        |
| Assia        |
| Boris        |
| Olimpia      |
| Jole         |
| Ivano        |
| Lauro        |
| Iacopo       |
| Mauro        |
| Shaira       |
| Gianleonardo |
| Erminia      |
| Leone        |
| Noemi        |
| Pietro       |
| Silverio     |
| Graziano     |
| Graziano     |
| Cassiopea    |
| Fortunata    |
| Maruska      |
| Claudia      |
| Giuliano     |
| Rita         |
| Timothy      |
| Fortunata    |
| Bibiana      |
| Vitalba      |
| Irene        |
| Zelida       |
| Bibiana      |
| Caligola     |
| Ileana       |
| Ausonio      |
| Clea         |
| Cleopatra    |
| Gaetano      |
| Gavino       |
| Egisto       |
| Carlo        |
| Vera         |
| Vania        |
| Ninfa        |
| Davis        |
| Adriano      |
| Danuta       |
| Noemi        |
| Carlo        |
| Ivano        |
| Isira        |
| Deborah      |
| Raniero      |
| Guendalina   |
| Anastasio    |
| Lidia        |
| Jelena       |
| Kris         |
| Leonardo     |
| Violante     |
| Gregorio     |
| Marieva      |
| Ingrid       |
| Concetta     |
| Valdo        |
| Danny        |
| Giulietta    |
| Giancarlo    |
| Carlo        |
| Bacchisio    |
| Ivano        |
| Terzo        |
| Grazia       |
| Alan         |
| Cleros       |
| Silverio     |
+--------------+
160 rows in set, 1 warning (0.00 sec)

### Use '%' after year for select also the data after the selector

2. Selezionare tutti i corsi che valgono più di 10 crediti (479) :
mysql> SELECT `name`
    -> FROM `courses`
    -> WHERE `cfu` > 10;
+------------------------------------+
| name                               |
+------------------------------------+
| provident aut non                  |
| quod in aut                        |
| beatae eveniet fugiat              |
| iure qui voluptas                  |
| quo et asperiores                  |
| corporis enim doloremque           |
| velit aut voluptatum               |
| ut rem libero                      |
| soluta voluptatem at               |
| vero est explicabo                 |
| maxime laboriosam nostrum          |
| consectetur aut odio               |
| accusantium culpa sint             |
| tempora voluptatum aut             |
| aliquam aliquam et                 |
| atque assumenda explicabo          |
| rerum quod quibusdam               |
| expedita praesentium alias         |
| iste ullam cum                     |
| voluptatum incidunt ut             |
| minus beatae illo                  |
| odio odit id                       |
| veniam dolorum dolor               |
| cupiditate deleniti nihil          |
| eligendi sed exercitationem        |
| officia esse maxime                |
| voluptas culpa eos                 |
| tempore molestiae et               |
| molestiae est neque                |
| qui eligendi non                   |
| dolorem laudantium minima          |
| quia aut aut                       |
| id id qui                          |
| molestias minima voluptates        |
| officiis sit sed                   |
| magni ea tempora                   |
| iusto consequatur ut               |
| facilis vero voluptatem            |
| ipsam amet recusandae              |
| sunt omnis asperiores              |
| quis quasi eos                     |
| ut nam cupiditate                  |
| et totam eius                      |
| et harum laboriosam                |
| laborum expedita ullam             |
| voluptas amet vitae                |
| optio corporis explicabo           |
| porro optio odit                   |
| adipisci ea enim                   |
| velit ut dolorem                   |
| quis aut a                         |
| magnam ullam doloribus             |
| eaque veritatis ea                 |
| assumenda et sed                   |
| sapiente quia accusantium          |
| a vero voluptatibus                |
| quod ut aliquid                    |
| eaque exercitationem non           |
| sit quis inventore                 |
| nesciunt esse natus                |
| ut voluptatibus neque              |
| qui ipsa non                       |
| impedit sunt qui                   |
| enim quas sint                     |
| provident mollitia saepe           |
| ratione aut quas                   |
| corporis odit sint                 |
| quo similique autem                |
| provident ea molestiae             |
| et quibusdam libero                |
| ut eum quia                        |
| similique similique et             |
| vel et aut                         |
| similique qui sapiente             |
| architecto deleniti temporibus     |
| sunt ut dolorem                    |
| voluptas excepturi aut             |
| ratione dolorem debitis            |
| exercitationem nostrum at          |
| et ea beatae                       |
| quia praesentium perferendis       |
| et autem exercitationem            |
| quo recusandae dignissimos         |
| deserunt delectus eos              |
| illum non accusamus                |
| voluptatem ipsa odit               |
| aperiam repellat doloremque        |
| facere laboriosam quod             |
| rem delectus eius                  |
| voluptatibus quo eligendi          |
| neque voluptas dolorum             |
| asperiores odit incidunt           |
| quo explicabo quae                 |
| voluptatem rem ut                  |
| nemo sit eum                       |
| numquam deserunt quasi             |
| nam id aliquid                     |
| sunt eum ipsam                     |
| nulla cupiditate nemo              |
| ea et harum                        |
| distinctio quo praesentium         |
| nihil vero voluptas                |
| maiores cumque repudiandae         |
| qui similique qui                  |
| quod et non                        |
| nemo quis omnis                    |
| sit officia accusamus              |
| inventore reiciendis deserunt      |
| aut ullam pariatur                 |
| fugit molestiae earum              |
| nisi illum vitae                   |
| provident cumque voluptatem        |
| officia nobis necessitatibus       |
| possimus earum qui                 |
| adipisci aliquam dolorum           |
| voluptatem quibusdam fugit         |
| placeat mollitia atque             |
| cumque doloribus ducimus           |
| et ducimus sed                     |
| voluptatem sit dolorem             |
| sed quis itaque                    |
| nesciunt quo mollitia              |
| est ab ratione                     |
| omnis rerum tenetur                |
| officiis corrupti et               |
| ducimus laborum aliquid            |
| voluptatibus omnis et              |
| expedita consequatur nihil         |
| ut dolorum soluta                  |
| debitis in quo                     |
| ut ea officia                      |
| veniam molestiae molestias         |
| ut facilis qui                     |
| unde non corporis                  |
| cum debitis assumenda              |
| ea facere laboriosam               |
| officia dolor a                    |
| eligendi corrupti tempore          |
| corrupti enim praesentium          |
| quisquam quo voluptas              |
| a quis at                          |
| aut consequatur exercitationem     |
| et nam aut                         |
| natus soluta eum                   |
| necessitatibus sed vel             |
| architecto id cum                  |
| sunt fuga qui                      |
| perferendis ipsa et                |
| fugit debitis sapiente             |
| iure impedit iusto                 |
| quia aspernatur dolorum            |
| voluptas veniam similique          |
| culpa nemo aut                     |
| animi aliquid consequatur          |
| dignissimos eos sit                |
| cum doloremque nostrum             |
| nesciunt eligendi sed              |
| et magni voluptas                  |
| vel deleniti tempore               |
| ea impedit quidem                  |
| aliquid ducimus optio              |
| saepe harum quidem                 |
| et sed eum                         |
| eligendi quia voluptatem           |
| sit atque nulla                    |
| commodi nam mollitia               |
| provident culpa labore             |
| error ut officiis                  |
| quas quo rem                       |
| ut dolores maiores                 |
| facere ad rerum                    |
| quidem rerum illum                 |
| vel molestiae sed                  |
| dolor laborum optio                |
| quod veritatis incidunt            |
| sapiente nihil et                  |
| illum ex doloremque                |
| laborum provident voluptatibus     |
| voluptates sed eaque               |
| quia porro consectetur             |
| sed quo delectus                   |
| molestiae est qui                  |
| rem adipisci dolorem               |
| et possimus assumenda              |
| amet dicta et                      |
| et iure natus                      |
| magnam saepe nihil                 |
| distinctio numquam illum           |
| ducimus sapiente at                |
| et est porro                       |
| et et saepe                        |
| quia eos doloremque                |
| ipsa aliquid sapiente              |
| est earum iure                     |
| esse harum quaerat                 |
| nesciunt et ullam                  |
| rerum voluptatibus iusto           |
| culpa quis expedita                |
| rerum vel voluptatem               |
| inventore praesentium voluptatem   |
| illum sit dolores                  |
| qui dignissimos quis               |
| atque et consectetur               |
| quidem voluptas est                |
| assumenda dolorum perspiciatis     |
| voluptate quos esse                |
| dolore enim eius                   |
| sed possimus expedita              |
| vitae vitae aperiam                |
| tempora nesciunt aut               |
| ipsa assumenda eligendi            |
| ab error incidunt                  |
| ut veritatis magnam                |
| dolor ab possimus                  |
| labore qui et                      |
| reiciendis molestiae qui           |
| modi sed earum                     |
| vero harum cupiditate              |
| culpa voluptas voluptatem          |
| ad molestiae necessitatibus        |
| nihil quia at                      |
| facilis adipisci provident         |
| totam illo non                     |
| facere adipisci sed                |
| non explicabo aut                  |
| quo dolor aspernatur               |
| accusamus et quidem                |
| quia voluptatibus nisi             |
| aperiam ut suscipit                |
| aut nesciunt deleniti              |
| error quia minus                   |
| dicta ducimus odit                 |
| ex molestiae rerum                 |
| quam voluptatem nihil              |
| labore sequi incidunt              |
| qui doloremque dolorem             |
| ut eius error                      |
| rerum aperiam ducimus              |
| sapiente pariatur voluptates       |
| velit esse soluta                  |
| tempore quod eum                   |
| accusamus nesciunt quia            |
| eum beatae earum                   |
| fuga at officiis                   |
| perspiciatis voluptates veniam     |
| similique id non                   |
| consequatur expedita voluptas      |
| est in officia                     |
| reiciendis totam quis              |
| amet qui quibusdam                 |
| necessitatibus sit neque           |
| asperiores eveniet maxime          |
| et in aspernatur                   |
| hic inventore a                    |
| dolores et est                     |
| ea quo itaque                      |
| est aspernatur et                  |
| sit voluptas rem                   |
| voluptas aliquid molestiae         |
| facere sit est                     |
| doloribus nemo iure                |
| aut cumque rerum                   |
| perspiciatis itaque rerum          |
| saepe laudantium quia              |
| et vero aspernatur                 |
| ut ut laboriosam                   |
| blanditiis sit doloribus           |
| natus unde quibusdam               |
| non voluptatibus quia              |
| nam aut reprehenderit              |
| totam expedita vel                 |
| unde veritatis a                   |
| quaerat id possimus                |
| quidem ipsa laborum                |
| illum est ea                       |
| natus dolores mollitia             |
| omnis voluptas molestias           |
| tenetur est et                     |
| voluptas exercitationem voluptates |
| magni in perferendis               |
| enim odit debitis                  |
| sed nostrum consequuntur           |
| non dolorem sequi                  |
| rerum cupiditate tempore           |
| sunt qui mollitia                  |
| animi nihil aliquam                |
| commodi praesentium repudiandae    |
| sint explicabo quae                |
| quidem provident praesentium       |
| rerum dignissimos et               |
| architecto eligendi consequatur    |
| ea enim adipisci                   |
| dolorum quos eum                   |
| aut reprehenderit deleniti         |
| iure qui et                        |
| commodi sint fugit                 |
| aspernatur fugiat reprehenderit    |
| odit odio veniam                   |
| magnam quis dolore                 |
| labore tempora odit                |
| qui nemo ad                        |
| quaerat accusamus eos              |
| qui quis quam                      |
| neque architecto est               |
| sapiente saepe porro               |
| exercitationem explicabo fuga      |
| voluptatem aliquam nam             |
| voluptatem consectetur voluptas    |
| dolorem nemo rem                   |
| minima aliquam numquam             |
| tempora laboriosam iusto           |
| enim id deserunt                   |
| molestiae incidunt facilis         |
| commodi suscipit perspiciatis      |
| nostrum fugiat optio               |
| magnam vel sed                     |
| voluptatem fuga incidunt           |
| explicabo quaerat ducimus          |
| est in quasi                       |
| dolorem blanditiis nemo            |
| temporibus tempore ipsam           |
| est illum inventore                |
| delectus omnis dolores             |
| est cum explicabo                  |
| iusto quibusdam et                 |
| est id hic                         |
| in perferendis non                 |
| iste in animi                      |
| ullam voluptatem facere            |
| quasi occaecati nulla              |
| ipsa sint omnis                    |
| quaerat et soluta                  |
| qui laboriosam molestiae           |
| sint quam unde                     |
| nobis delectus veritatis           |
| quidem minus minus                 |
| harum illo consequatur             |
| minus maiores porro                |
| qui nemo in                        |
| blanditiis numquam quos            |
| nemo fugiat rerum                  |
| omnis culpa voluptatem             |
| est omnis possimus                 |
| consequatur est numquam            |
| atque non numquam                  |
| fuga pariatur excepturi            |
| voluptatem architecto alias        |
| nihil omnis et                     |
| voluptatem perferendis repellendus |
| eveniet rerum minima               |
| earum numquam deserunt             |
| labore dolorem ipsa                |
| est explicabo iste                 |
| commodi laboriosam cumque          |
| amet quod repudiandae              |
| voluptas dolores quos              |
| et doloribus qui                   |
| rerum deserunt eaque               |
| cupiditate ullam earum             |
| assumenda impedit nihil            |
| nam ratione officiis               |
| dolor repellat dignissimos         |
| distinctio ullam aspernatur        |
| quasi fugit est                    |
| nobis aut voluptas                 |
| quis aperiam ab                    |
| quia consectetur consequatur       |
| porro aliquid est                  |
| natus quia recusandae              |
| veniam unde laborum                |
| at dolorem temporibus              |
| doloribus iusto quia               |
| est et in                          |
| ut sint qui                        |
| alias iure possimus                |
| numquam aspernatur nesciunt        |
| nihil ipsa et                      |
| labore rerum deleniti              |
| rem ut ea                          |
| vel et dolores                     |
| illum ad quos                      |
| quisquam error aut                 |
| fugit quis rerum                   |
| eius provident sapiente            |
| quaerat in ut                      |
| ut quo ducimus                     |
| et occaecati eius                  |
| sit assumenda ut                   |
| enim quae quos                     |
| distinctio rerum dolor             |
| et earum tenetur                   |
| et enim occaecati                  |
| iusto consequatur quae             |
| sequi temporibus aut               |
| ea eos dolor                       |
| voluptatem repudiandae rerum       |
| eos est dolor                      |
| architecto atque dolorem           |
| enim voluptate perferendis         |
| voluptas hic laboriosam            |
| soluta alias fugiat                |
| aut debitis nesciunt               |
| ex perspiciatis blanditiis         |
| porro illo ea                      |
| facere explicabo quam              |
| ullam ducimus architecto           |
| sunt culpa id                      |
| vel ipsa eos                       |
| ut qui reiciendis                  |
| et eius occaecati                  |
| porro autem cumque                 |
| ex quaerat commodi                 |
| omnis quibusdam et                 |
| autem tempora ipsa                 |
| corporis harum maxime              |
| in blanditiis dolorum              |
| consequatur fugiat quia            |
| quos pariatur aliquid              |
| culpa nulla aut                    |
| aliquam molestias sit              |
| consequuntur aut pariatur          |
| et deserunt vitae                  |
| enim cupiditate laudantium         |
| dolores dolor voluptas             |
| ut quis illo                       |
| consequatur aperiam illo           |
| consequatur in ratione             |
| accusantium aut dicta              |
| iure alias at                      |
| quia error voluptates              |
| quas est repellat                  |
| consequatur occaecati illo         |
| eum et saepe                       |
| ipsa quas quia                     |
| facilis magnam rem                 |
| necessitatibus consequatur aperiam |
| magnam voluptatem harum            |
| rerum et qui                       |
| ex totam sint                      |
| vel velit non                      |
| quas cum vel                       |
| nostrum atque ipsa                 |
| consequatur architecto consequatur |
| eaque dolores est                  |
| eius eum itaque                    |
| sunt consequatur soluta            |
| nihil consectetur ex               |
| eveniet qui cumque                 |
| molestiae aut sit                  |
| incidunt aperiam qui               |
| aut dolorum distinctio             |
| fugit distinctio quibusdam         |
| autem possimus illum               |
| officia cumque tempore             |
| voluptas sit aliquam               |
| amet itaque fugit                  |
| doloribus debitis eveniet          |
| adipisci ut quis                   |
| voluptas corporis recusandae       |
| unde at voluptas                   |
| exercitationem ea omnis            |
| accusantium tempora vel            |
| praesentium mollitia rerum         |
| qui sapiente voluptatem            |
| quia non rerum                     |
| reiciendis dolorum labore          |
| laboriosam aperiam ut              |
| et fugit occaecati                 |
| repudiandae amet similique         |
| debitis est saepe                  |
| molestiae distinctio quis          |
| quaerat in qui                     |
| minus expedita et                  |
| consectetur aut est                |
| unde commodi qui                   |
| porro et aut                       |
| qui vitae molestias                |
| enim unde dolorem                  |
| sit amet voluptatum                |
+------------------------------------+
479 rows in set (0.00 sec)
