---
updatedAt: 2026-10-22T13:40:38.000Z
agentTools:
  projectIndex: https://appsflyerkb-group.readme.io/marketers/llms.txt
---

# Импорт данных о затратах

<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. Вы можете проверить, включена ли функция в ваш план, на странице управления аккаунтом. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Cost Import, part of AppsFlyer ROI360, allows advertisers to get full and accurate coverage of their marketing cost by importing CSV files via upload or email.

## Обзор

Используйте импорт данных о затратах, чтобы:

- Передавать в AppsFlyer затраты на кампании, направленные на любые маркетинговые цели (мобильные кампании, кампании с привлечением блогеров, CTV и т. д.). Это особенно важно для медиаисточников, которые не сообщают о затратах через API или по ссылке атрибуции.
- Ретроактивно перезаписывать и корректировать ранее полученные данные о расходах.

Данные о расходах передаются в AppsFlyer в CSV-файлах, загружаемых в систему или отправляемых по электронной почте. Как только AppsFlyer получает файл, данные обрабатываются и становятся доступными на дэшбордах и в отчетах в течение нескольких часов. Так вы получаете полное представление о ROI и затратах на кампанию.

**Примечание**:

- Рекламные сети могут импортировать файлы с затратами для своих клиентов при наличии соответствующих разрешений.
- Агентства не могут загружать данные. Они могут подготовить свои файлы и отправить их рекламодателю для загрузки.

## Процедуры

Чтобы воспользоваться Импортом затрат и отправить данные о затратах в AppsFlyer, вам нужно:

1. [Prepare the CSV file](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#prepare-csv-file-with-cost-data) with the cost data to send.
2. Отправить файл в AppsFlyer через:
   - [Uploading](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#email-file) it in the AppsFlyer UI.
   - [Email](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#email-file). **Note**: For apps on CTV, PC, and console platforms, use only this method.

Подробные инструкции см. в следующих разделах.

<div id="prepare-csv-file-with-cost-data" />

<Accordion title="Prepare CSV file with cost data">

Рекламодатели, рекламные сети и агентства могут подготовить CSV-файл для импорта затрат. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">См. пример файла</Anchor>

**Как подготовить CSV-файл**:

- Следуйте рекомендациям по схеме, формату и правилам для файла, подробно описанным в следующих таблицах.  
  При желании вы можете добавить к данным о стоимости сведения о кликах и показах, сообщаемых рекламной сетью. **Note**: If you use Excel or Google Sheets to create the file, follow the [Excel and Google Sheets formatting instructions](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file).

#### Схема CSV

<table><thead><tr><th><p><span>Column name </span></p><p><span>(case sensitive)</span></p></th><th><span>Format/remark</span></th><th><span>Example</span></th><th><span>Mandatory</span></th></tr></thead><tbody><tr><td><span>date</span></td><td><ul><li><span>Дата расходов</span></li><li><span>Формат: Строка</span><br/><span>Практические рекомендации:</span><ul><li><span>YYYY-MM-DD</span></li><li><span>YYYY/MM/DD</span></li><li><span>MM-DD-YYYY</span></li><li><span>MM/DD/YYYY </span><br/> </li></ul></li><li>Даты в будущем не допускаются</li><li><strong>Рекомендация</strong>: Используйте тот же часовой пояс, который определен для вашего приложения в AppsFlyer.</li><li>Примечание: Используете Excel/Google sheets для подготовки файла? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">Прочитайте это</a>. </li></ul></td><td><ul><li><span>05.2019.30</span></li><li><span>2019/05/30</span></li><li><span>30.5.2019</span></li><li>5/30/2019</li><li>05-30-2019</li><li>05/30/2019</li></ul></td><td><span>✓</span></td></tr><tr><td><span>app-id</span></td><td><ul><li><span>Формат: Строка</span></li><li><span>Идентификатор приложения, как он отображается в AppsFlyer</span>.</li><li>В одном файле допускаются несколько идентификаторов приложений.</li><li>Все идентификаторы приложений должны принадлежать одному аккаунту рекламодателя.</li></ul></td><td><ul><li><span>com.app.name </span></li><li><span>id12356789</span></li></ul></td><td><span>✓</span></td></tr><tr><td><span>media-source</span></td><td><ul><li><span>Формат: Строка</span></li><li><span>Media source name <strong>exactly</strong> as it appears in AppsFlyer. <strong>Note:</strong> Include the _int suffix if relevant.</span></li><li><span>Для одного файла допускается только один медиаисточник. </span><span></span>Допускаются несколько приложений для одного и того же медиаисточника</li></ul></td><td><span>network_x_int</span></td><td><span>✓</span></td></tr><tr><td><span>campaign</span></td><td><ul><li><span>Format: String</span><span></span></li><li><span>Название кампании. Если в рекламной сети отображается название кампании, название в этом файле должно совпадать с ним (с учетом регистра).</span></li><li>Не используйте одно и то же название кампании для нескольких приложений.</li></ul></td><td>campaign_a</td><td><p><span>✓</span></p><p><span><strong>Note</strong>: If attribution data exists with both name and ID, the CSV must contain both to match.</span></p></td></tr><tr><td><span>spend</span></td><td><ul><li><span>Monetary cost</span></li><li><span>Допускается до пяти знаков после десятичной запятой.</span></li><li><span>Допускается значение 0 (ноль)</span></li><li><span><strong>Note</strong>: </span><ul><li>Не допускается использование запятых в качестве разделителя групп разрядов, например: «2,874.12».</li><li>Используете Excel/Google Таблицы для подготовки файла? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">Прочитайте это</a>.</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><span><span>✓</span></span></td></tr><tr><td><span>reported-clicks</span></td><td><ul><li><span>Format: Integer</span></li><li><span>Количество кликов по данным рекламной сети.</span></li><li><span>Только целые числа. Без десятичных дробей, разделителей-запятых, символов валют или экспоненциальной записи.</span></li><li><span>Значение должно быть 0 или больше. Допускается значение 0.</span></li></ul></td><td><span>1200</span></td><td><span>No</span></td></tr><tr><td><span>reported-impressions</span></td><td><ul><li><span>Format: Integer</span></li><li><span>Количество показов по данным рекламной сети.</span></li><li><span>Только целые числа. Без десятичных дробей, разделителей-запятых, символов валют или экспоненциальной записи.</span></li><li><span>Значение должно быть 0 или больше. Допускается значение 0.</span></li></ul></td><td><span>45000</span></td><td><span>No</span></td></tr><tr><td><span>geo</span></td><td><ul><li><span>Формат: Строка</span></li><li><span>Двухбуквенный код страны в соответствии с </span><a href="https://www.iso.org/iso-3166-country-codes.html"><span>ISO 3166</span></a><span>. <strong>Примечание</strong>: Убедитесь, что вы отправили 2 символа без пробелов.</span></li><li><span>For the United Kingdom use UK,</span><span> not GB.</span><br/> </li></ul></td><td><p><span>US, CN, AU</span></p></td><td><span>No</span></td></tr><tr><td><span>currency</span></td><td><ul><li><span>Формат: Строка</span></li><li>Код валюты из трех символов по стандарту <a href="https://www.iso.org/iso-4217-currency-codes.html" target="_blank">ISO-4217</a>. <strong>Примечание</strong>: убедитесь, что значение состоит ровно из трех символов, без пробелов в начале и конце.</li><li><span>Разрешается использовать один код валюты для каждого приложения в файле. </span><span>В разных приложениях могут быть разные коды валют. </span>.</li></ul></td><td><span>USD, GBP, EUR, JPY</span></td><td><p><span>Нет.</span></p><p><span>Если оставить поле пустым, по умолчанию будет использоваться USD.</span></p></td></tr><tr><td><span>campaign-id</span></td><td>Формат: Строка</td><td>abc1234def</td><td rowspan="5"><p>№</p><p><strong>Примечание</strong>: если данные атрибуции содержат и название, и идентификатор, для корректного сопоставления в CSV-файле необходимо указать оба значения.</p></td></tr><tr><td><span>adset</span></td><td>Формат: Строка </td><td>my_adset_1</td></tr><tr><td><span>adset-id</span></td><td>Формат: Строка</td><td>id5678ghi</td></tr><tr><td><span>ad</span></td><td>Формат: Строка </td><td>my_ad_name</td></tr><tr><td><span>ad-</span><span>id</span></td><td>Формат: Строка </td><td>id91011jkl</td></tr><tr><td><span>site-id</span></td><td><ul><li>Формат: Строка </li><li>Уникальный идентификатор, определяющий издателя, показывающего рекламу. <a href="./about-link-structure-and-parameters#site-id-parameter" target="_blank">Узнать больше</a></li></ul></td><td>id1213mno</td><td>Ни один</td></tr><tr><td><span>channel</span></td><td>Формат: Строка </td><td> video</td><td>Ни один</td></tr><tr><td><span>keywords</span></td><td>Формат: Строка</td><td><ul><li>better</li><li>better you app</li><li>better you online</li></ul></td><td>Ни один</td></tr><tr><td><span>agency</span></td><td><ul><li>Формат: Строка</li><li>Название агентства. Значение в параметре <code>af_prt</code>.</li><li>В одном файле можно указать только одно агентство и только кампании, которыми оно управляет.</li><li>Название агентства является обязательным для каждой строки. В столбце агентство не допускаются пустые ячейки.</li><li>Агентство должно иметь разрешение на все приложения, включенные в файл.</li><li>Загрузить файл могут только рекламодатели. Агентства не могут загружать данные. Они могут подготовить свои файлы и отправить их рекламодателю для загрузки.</li><li>Если повторно отправить данные о расходах за те же даты, добавив название агентства (<code>af_prt</code>), которого не было в исходном файле, данные о расходах будут продублированы.</li></ul></td><td>Название агентства</td><td>Ни один</td></tr><tr><td colspan="4"><span><strong>Note:</strong> Names with non-English characters must be encoded using UTF-8.</span></td></tr></tbody></table>

#### Формат CSV-файла и правила его заполнения

| Правило                | Требования                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Запрещенные символы    | Fields in string format can't have `=`, `+`, `-`, or `@` as the first character. For example, `@example_campaign` or `=123` are prohibited.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Владелец приложения    | Допускается один рекламодатель (владелец приложения) на файл. Допускаются несколько приложений от одного аккаунта рекламодателя.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Расширение имени файла | Пример CSV: abc123.csv                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Структура файла        | <ul><li>**Format**: Files have a CSV format meaning that each column is separated by a comma.</li><li>**Header row**: The first row is a header row that matches the schema</li><li>**Data rows**: Contain the mandatory columns. **Note**: Make sure that there are no trailing blanks in your data. For example, [USD] (a blank follows the **D** should be changed to [USD].</li><li>**Blank rows**: Not permitted</li><li>**Duplicate rows** having the same key: Not permitted. Ключ формируется на основе обязательных полей.</li><li>**Blank cells:** Empty values are not allowed in the file. Если вы не хотите загружать определенные поля, их не должно быть в файле.</li></ul> |
| Иерархия рекламы       | Затраты должны учитываться на уровне кампании, а другие параметры в рекламной иерархии являются необязательными.<br /><br />Любые неполные данные, загруженные на более низком уровне иерархии, перезапишут все данные начиная с уровня кампании и ниже.<br /><br />**For example:** If you import a file with campaign cost for adset 1, and separately import another file for adset 2 of the same campaign, the total cost of the campaign will be replaced and show only adset 2 data. Чтобы рассчитать общую стоимость кампании, в импортируемом файле должны присутствовать adset 1 и adset 2.       |

</Accordion>

<div id="upload-file" />

<Accordion title="Upload file">

Рекламодатели и рекламные сети могут загружать CSV-файлы для импорта затрат.

**Prerequisites**: Ad networks require [Cost Import permission from the advertiser](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#cost-import-permissions-for-ad-networks).

**Для загрузки CSV файла через AppsFlyer UI**:

1. In AppsFlyer, from the side menu, select **Settings** > **Cost Import.**  
   The Cost Import page displays.
2. Click **+ Import cost file**  
   The Import cost window opens.
3. Drag the CSV file to the **Import cost file** window.  
   Появится сообщение об обработке файла.
4. Если во время загрузки отображается сообщение об ошибке: устраните ее и повторите соответствующие действия.
5. The **Cost Import: file summary** window opens.
6. Выполните одно из следующих действий:
   - Abort the upload, click **Cancel import**.
   - Complete the import process, click **Import file.**  
     The message, All set! отображается.
   - If an error message displays, follow the [error message instructions](#error-messages-and-solutions).
7. Click **Import another file** or **Done**.

</Accordion>

<div id="email-file" />

<Accordion title="Email file">

Рекламодатели и рекламные сети могут отправлять CSV-файлы с данными о расходах по электронной почте.

**Необходимые условия**:

- **Рекламодатели**:
  - Электронная почта отправителя должна принадлежать зарегистрированному пользователю AppsFlyer.
- **Рекламные сети**:
  - Электронная почта отправителя должна принадлежать зарегистрированному пользователю AppsFlyer.
  - [Cost Import permission from the advertiser](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#cost-import-permissions-for-ad-networks).

**Чтобы отправить файл CSV по электронной почте**:

1. Get the [token for email import](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#token-for-email-import).
   1. In AppsFlyer, from the side menu, select **Settings** > **Cost Import.**
   2. In the upper right-hand of the page, click **Token for email import.**
   3. Скопируйте и сохраните токен.
2. Составьте электронное письмо со следующими полями:
   - **To**:`adspend-upload@appsflyer.com`
   - **CC:** **Users who should get a copy of the automatic feedback**
   - **Subject**: Paste the token for email import in the subject field.
   - **Attachment**: CSV file with the data.
3. Отправить письмо.
   - После получения и обработки файла генерируется статусное письмо с итогами, деталями, проблемами или ошибками, обнаруженными в процессе обработки. Письмо отправляется всем участникам, указанным в письме, и администратору рекламодателя. Where errors are identified, follow the [error message instructions](#error-messages-and-solutions).
   - You can view the status of files submitted on the [Cost Import dashboard](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#error-messages-and-solutions)

</Accordion>

## Дэшборд

Дэшборд импорта затрат позволяет загружать файлы и просматривать сведения о ранее загруженных файлах.

<div id="cost-import-dashboard" />

<Accordion title="Cost Import dashboard">

To view the Cost Import dashboard, in AppsFlyer, from the side menu, select **Settings** > **Cost Import**.

В следующей таблице описана информация, доступная о ранее импортированных файлах.

| Название столбца                             | Описание                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Название CSV-файла                           | Название файлов затрат, импортированных в AppsFlyer.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Дата загрузки                                | Дата импорта файла.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Подписка IAP                                 | Медиаисточник, включенный в файл.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Диапазон дат                                 | Первая и последняя даты в файле, за которые указаны расходы на рекламу.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Сопоставленные строки (%) | Процент строк в файле, где затраты были сопоставлены с атрибуцией. [Learn more](#matched-rows).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| В. Статус                    | The status of the imported file:<ul><li>**Success**: Action completed successfully. Затраты зафиксированы и доступны в дэшбордах и отчетах AppsFlyer.</li><li>**Validation error**: AppsFlyer system problem. Подождите 10 минут и повторите попытку. При повторном сбое обратитесь в службу поддержки AppsFlyer.</li><li>**No permissions**: The token is not approved for this app.<ul><li>Рекламодатели: Убедитесь, что использован правильный идентификатор приложения.</li><li>Рекламные сети: Проверьте, чтобы рекламодатель, дал вам разрешение на импорт затрат.</li></ul></li><li>**Reverted**: Action completed successfully. Файл был перезаписан/заменен другими данными.</li></ul> |
| Действие                                     | <ul><li>At the file level: If you have app permissions to all the apps contained in the file, you can:<ul><li>**Download CSV file**: This a copy of the imported CSV file.</li><li>**Download unmatched report** for all apps in the file. Дополнительную информацию см. в разделе «Сопоставленные строки» этой таблицы.</li></ul></li><li>На уровне приложения: Если вы нажмете на конкретный файл, отобразится информация обо всех импортируемых затратах для приложения из этого конкретного файла, а также из других файлов. If you have app permission for the app you can:<ul><li>**Download app data.**</li><li>**Download unmatched report** for the app</li><li>**Revert** (cancel) the Cost Import for the selected app.</li></ul></li></ul>                                                                                                                                                                                                                          |

</Accordion>

<div id="matched-rows" />

<Accordion title="Matched rows">

Сопоставление строк — это процесс, при котором данные о расходах, полученные в результате импорта, сопоставляются с данными атрибуции, зарегистрированными в AppsFlyer. Для этого используются названия (не идентификаторы) всех доступных параметров, таких как медиаисточник, кампания, группа объявлений, объявление и т. д. Если все они совпадают, то строки обозначаются как is-matching=TRUE.

Данные о расходах регистрируются и отображаются в дэшбордах и отчетах AppsFlyer независимо от статуса сопоставления.

Процент сопоставленных строк отображается на дэшборде импорта затрат. Если наличие несопоставленных не соответствует ожидаемому или доля сопоставленных строк (%) оказалась выше ожидаемой:

- Загрузите отчет о Несопоставленных данных, чтобы выяснить причину. Отчет о Несопоставленных данных содержит столбец «is-matched», который может иметь значение TRUE (сопоставлены) или FALSE (не сопоставлены).
- При необходимости отмените импорт, сбросив его.
- Смотрите раздел «Действие» в этой таблице для получения более подробной информации.

</Accordion>

## Информация

<div id="using-excel-or-google-sheets-to-prepare-csv-file" />

<Accordion title="Using Excel or Google Sheets to prepare CSV file">

При использовании Excel или Google Таблиц для подготовки CSV-файла необходимо правильно отформатировать столбцы даты и расходов перед сохранением файла в формате CSV. После сохранения CSV-файла проверьте правильность форматирования его содержимого. Используйте следующие рекомендации чтобы:

- отформатировать ячейки с датами.;
- отформатировать ячейки с затратами;
- проверить формат содержимого.

#### Форматирование ячеек с датами

**Чтобы отформатировать ячейки даты в Excel в формате ГГГГ-ММ-ДД**:

1. Выберите ячейки, которые необходимо отформатировать.
2. Right-click and then select **Format cells**.  
   Откроется окно форматирования ячеек.   <Image alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. Select **Custom**.
4. In the Type field, enter **YYYY-MM-DD**
5. Click **OK**.  
   Дата отформатируется.

#### Форматирование ячеек с затратами

Обычно Excel форматирует ячейки со значениями с помощью запятой для отделения тысяч, как показано на следующем изображении. Этот формат не подходит для файлов импорта затрат.

<Image alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

**Чтобы отформатировать ячейки с расходами без запятых в качестве разделителей тысяч**:

1. Выберите ячейки, которые необходимо отформатировать.
2. Right-click and then select **Format cells**.  
   Откроется окно форматирования ячеек.
3. Select **Number**.   <Image alt="Formatnumbers.png" src="https://files.readme.io/d2bfeec87d24739e9d1cea8467d7ce23b56aa9414a96202379f6e774991bf387-360004075458.png" width="381px" />
4. Clear **Use 1000 separator (,).**
5. (Optional) Set the number of **Decimal places**. По умолчанию установлено значение 2. Максимально допустимое значение — 5.
6. Click **OK**.  
   Ячейки отформатированы правильно.

#### Проверьте формат содержимого

**Чтобы проверить формат содержимого**:

1. Используйте редактор для просмотра файла.
   - Windows: Блокнот, Notepad++
   - macOS: TextEdit
2. Обратите особое внимание на следующее:
   - **Blank spaces:** Make sure that there are no leading or trailing blank spaces before or after the commas that separate the fields. В Excel используйте функцию TRIM для удаления лишних пробелов.
   - **Date:** Make sure that the date cells have the format YYYY-MM-DD.
   - **Spend:** Make sure there are no commas in the spend cells.
   - **Delimiters**: Must be commas. Если в качестве разделителей используются точки с запятой:
     - Это может происходить, когда в региональных настройках компьютера установлен язык/регион, отличный от английского, особенно часто это случается при выборе немецкого.
     - Способ решения зависит от операционной системы вашего компьютера (macOS или Windows).
     - Чтобы решить эту проблему, найдите последние рекомендации на форумах <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> или других аналогичных форумах. Используйте следующие поисковые запросы: Операционная система (macOS или Windows) Excel меняет разделитель для файлов CSV.

The following image contains a screenshot of the [sample CSV file](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv) displayed in an editor.

<Image alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

</Accordion>

<div id="token-for-email-import" />

<Accordion title="Token for email import">

Токен для импорта по электронной почте используется для проверки авторизации отправителя электронного сообщения для отправки файла импорта затрат.

Токены рекламодателей и рекламных сетей различаются.

- Токен рекламодателя:
  - Один и тот же токен действителен для всех приложений в аккаунте.
  - Токен может получить любой пользователь аккаунта.
- Токен рекламной сети:
  - Для всех рекламодателей используется один и тот же токен.

Рекламодатели и рекламные сети не должны делиться своими токенами друг с другом!

</Accordion>

<div id="cost-import-permissions-for-ad-networks" />

<Accordion title="Cost Import permissions for ad networks">

Рекламным сетям требуется разрешения рекламодателя на каждое приложение для доступа к импорту затрат.

**Чтобы предоставить рекламной сети разрешение на импорт затрат:**

1. In AppsFlyer, the **advertiser** needs to go to the side menu and select **Collaborate** > **Active Integrations.**  
   The Integrated Partner page displays.
2. Выберите интегрированного партнёра.
3. Go to the **Permissions** tab.
4. Enable **Ad Network Permissions** if it is not already so.
5. (необязательно) Добавить пользователей аккаунта.
6. Enable **Use Cost Import.**
7. Click **Save permissions**.

</Accordion>

## Поиск и устранение неполадок, особенности и ограничения

<div id="error-messages-and-solutions" />

<Accordion title="Error messages and solutions">

В следующей таблице перечислены все возможные сообщения об ошибках при импорте затрат и соответствующие решения.

| Сообщение об ошибке                                                                                                                                                                                                                                                                                                           | Описание                                                                                                                                                                                                  | РЕШЕНИЕ                                                                                                                                                                                                                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ни один из идентификаторов приложений, указанных в файле, не существует в AppsFlyer. Проверьте правильность идентификаторов приложений.                                                                                                                                                       | Идентификатор приложения не существует в аккаунте.                                                                                                                                        | Измените идентификатор приложения и отправьте повторно.                                                                                                                                                                                                                                                               |
| Строка [название строки] имеет неправильное количество столбцов. Ожидалось [количество] столбцов, получено [количество] столбцов. | Все столбцы в файле должны иметь значение.                                                                                                                                                | Измените значения, заполненные в файле, в соответствии с определенными заголовками.                                                                                                                                                                                                                                   |
| Отсутствует медиаисточник в заголовке файла.                                                                                                                                                                                                                                                                  | <ul><li>Отсутствует медиаисточник в заголовке файла.</li><li>Название столбца должно быть точно таким, как в схеме.</li></ul>                                                                             | Добавьте медиаисточник в качестве названия заголовка.                                                                                                                                                                                                                                                                 |
| Файл может содержать только один медиаисточник. В файле обнаружено несколько медиаисточников: [количество медиаисточников].                                                                                               | Файл содержит более одного медиаисточника. Скрытые пустые строки или неправильно оформленные строки в CSV также могут вызвать эту ошибку, даже если они не видны в Excel. | Откройте файл в текстовом редакторе, например, Notepad++, и удалите все пустые строки и неправильно сформированные ряды. Сохраните файл и загрузите его снова. Если файл содержит более одного медиаисточника, разделите его так, чтобы на каждый медиаисточник приходился один файл. |
| Значение [value], указанное для поля [field], не соответствует допустимому формату данных в этом столбце.                                                                                             | Неправильный формат данных в столбце. Например, вместо гггг-мм-дд дата указана как дд-мм-гг.                                                                              | Исправьте формат и отправьте повторно.                                                                                                                                                                                                                                                                                |
| Для приложения определено несколько валют. Используйте одну валюту для каждого приложения в файле. Обнаруженные валюты: %number of currencies%.                                                                                                               | Для одного приложения может использоваться только одна валюта.                                                                                                                            | Используйте одну валюту для загрузки и повторной отправки.                                                                                                                                                                                                                                                            |
| Следующие столбцы в заголовке файла не поддерживаются: [заголовки файлов].                                                                                                                                                                | Заголовок файла не соответствует схеме. То есть имя столбца должно быть точно таким, как в схеме.                                                                         | Удалите неподдерживаемые столбцы и отправьте повторно.                                                                                                                                                                                                                                                                |
| Отсутствуют необходимые столбцы в заголовке файла: [заголовки файла].                                                                                                                                                                     | В заголовке файла отсутствует обязательный столбец.                                                                                                                                       | Добавьте недостающий столбец и его значения и отправьте повторно.                                                                                                                                                                                                                                                     |
| В приложении указана будущая дата: [дата]                                                                                                                                                                                                                 | Даты в будущем не допускаются.                                                                                                                                                            | Исправьте дату на сегодняшнюю или более раннюю и отправьте повторно.                                                                                                                                                                                                                                                  |
| В файле нет данных. Нет данных для обработки.                                                                                                                                                                                                                                                 | В файле нет данных.                                                                                                                                                                       | Заполните данные в файле и отправьте повторно.                                                                                                                                                                                                                                                                        |
| Следующие две строки конфликтуют, поскольку содержат одинаковые значения параметров. Предоставьте одну строку расходов для каждого набора параметров. [конфликтующие строки].                                             | Имеется более одной строки с одинаковыми ключевыми (обязательными) полями.                                                                                             | Удалите дублирующиеся строки и отправьте повторно.                                                                                                                                                                                                                                                                    |
| Файл может содержать данные только от одного аккаунта рекламодателя. В файле встречаются различные рекламодатели: [имена рекламодателей].                                                                                 | У партнеров загрузка не может быть более чем для одного рекламодателя.                                                                                                                    | Разделите загрузку на отдельные файлы для каждого рекламодателя.                                                                                                                                                                                                                                                      |
| Приложения [ID приложения] нет в аккаунте. Проверьте идентификатор приложения.                                                                                                                                                            | Идентификатор приложения не существует.                                                                                                                                                   | Исправьте идентификатор приложения и отправьте повторно.                                                                                                                                                                                                                                                              |
| Для приложения [ID приложения] не найден код региона (страны). Используйте код из двух букв по ISO 3166.                                                                                                               | Гео не существует.                                                                                                                                                                        | Исправьте регион и отправьте повторно.                                                                                                                                                                                                                                                                                |
| Не найден код валюты для приложения [ID приложения]. Используйте код из трех букв по ISO 4217.                                                                                                                                            | Валюта не существует                                                                                                                                                                                      | Укажите допустимый код валюты и отправьте файл повторно.                                                                                                                                                                                                                                                              |
| Для одного или нескольких приложений в файле обнаружены ошибки проверки. Пожалуйста, ознакомьтесь с информацией о файле для более подробной информации.                                                                                                                                       | В файле имеется более одной ошибки.                                                                                                                                                       | Загрузите файл и проверьте его на наличие ошибок.                                                                                                                                                                                                                                                                     |
| При обработке файла произошла внутренняя ошибка, попробуйте загрузить его еще раз.                                                                                                                                                                                                                            | <ul><li>Backend issue processing the file.</li><li>Как правило, это временная проблема.</li></ul>                                                                                                         | Подождите 1 час и снова загрузите файл.                                                                                                                                                                                                                                                                               |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Характеристика                                                                                                                                                                                                    | Специфика                                                                                                                                                                                                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Рекламным сетям                                                                                                                                                                                                   | Supported.<br /><br />Exceptions:<ul><li>Meta Ads</li><li>X Ads</li><li>ASA</li></ul>                                                                                                                                                                                                                                                  |
| Агентства                                                                                                                                                                                                         | <ul><li>Агентства не могут загружать данные. Они могут подготовить свои файлы и отправить их рекламодателю для загрузки.</li><li>The CSV files must contain an Agency column with the agency name (the agency name is the value in the af\_prt parameter). [See CSV schema](https://appsflyerkb-group.readme.io/marketers/docs/import-cost-data#csv-schema)</li></ul> |
| Прозрачность агентства                                                                                                                                                                                            | Не поддерживается                                                                                                                                                                                                                                                                                                                                                      |
| Часовой пояс приложения                                                                                                                                                                                           | Поддерживается                                                                                                                                                                                                                                                                                                                                                         |
| Валюта приложения                                                                                                                                                                                                 | поддерживается. Расходы на кампанию конвертируются в валюту конкретного приложения.                                                                                                                                                                                                                                                    |
| Доступно только в <a href="https://support.appsflyer.com/hc/en-us/articles/45424430660497-About-Data-Locker-Advanced-Reports" target="_blank" rel="noopener noreferrer"> расширенных отчётах</a>. | The same campaign name can't be used for multiple apps, or the cost of one app will apply to both.                                                                                                                                                                                                                                                     |
| Названия полей                                                                                                                                                                                                    | Если названия полей в иерархии кампании не совпадают с названиями полей в данных атрибуции, то они будут учитываться отдельно. <br /><br />Например, если названия кампаний не совпадают, то, несмотря на одинаковые идентификаторы кампаний, они будут считаться разными кампаниями.                                                  |
| Размер файла                                                                                                                                                                                                      | When uploading a CSV Cost Import file the size limit is:<ul><li>Via AppsFlyer dashboard: 2 MB</li><li>Via email: 5 MB per file</li></ul>                                                                                                                                                                               |
| Неорганические данные                                                                                                                                                                                             | Поддерживается                                                                                                                                                                                                                                                                                                                                                         |
| Органические данные                                                                                                                                                                                               | Поддерживается                                                                                                                                                                                                                                                                                                                                                         |
| Актуальность данных                                                                                                                                                                                               | <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Ad spend</Anchor>                                                                                                                                                                                                                                     |
| Актуальность данных                                                                                                                                                                                               | поддерживается. Утвержденные расходы могут быть отменены и скорректированы в течение 90 дней.                                                                                                                                                                                                                                          |
| Тип периода подписки                                                                                                                                                                                              | Не поддерживается                                                                                                                                                                                                                                                                                                                                                      |
| Доступ пользователей аккаунта                                                                                                                                                                                     | Недоступно для пользователей с ограничениями по региону или медиаисточникам.                                                                                                                                                                                                                                                                           |

</Accordion>

> 📄 **See also**
>
> - <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Структура и параметры ссылки атрибуции</Anchor>
> - Сопоставленные строки

<div data-zendesk-anchors="ad-spend-import=overview 01H7VYHJ2BN3EFDC4J3YN3P4WM=overview h_01HYZBZMNTM0244V4PN6AJ45KR=procedures h_01HYZD52VRTMGJ0BFBFJNGQ50E=prepare-csv-file-with-cost-data ad-spend-csv-schema=csv-schema 01H7VYHJ2CWF2HWHCTZDEZHT29=csv-schema h_01HYZEDYKCAPTK1WD6VGWTA6PQ=csv-format-and-rules h_01HYZD52VRWK7D6Q0YBW9SEFK6=upload-file h_01HYZKN3YEPFG8525GFQD0PC5K=email-file h_01HZ4NVKPVHV1KT12V59MZBGPZ=dashboard h_01HZ1SXQQ2CHG77KX96D74J6TQ=cost-import-dashboard h_01HZ4NVKPVSM5ZTG76HJF3GW4J=matched-rows h_01HYZFNKFEQW13F0BWAG3FZF69=additional-information h_01HYZFNKFE3AVH1GNGDT511M5B=using-excel-or-google-sheets-to-prepare-csv-file formatting-date-cells-in-excel=format-date-cells 01H7VYHJ2DSWC2J1NY04Q9Q620=format-date-cells formatting-spend-cells-in-excel=formatting-spend-cells 01H7VYHJ2DA9JM4Q33V2TF7BD3=formatting-spend-cells h_01HYZJJVC463C141AQ3VY5Z0TQ=verify-content-format h_01HYZFNKFEXK4CYRBZ3ABRCWNJ=token-for-email-import h_01HZ1XV6ZX5FAN9JJPQM9RYD3Z=cost-import-permissions-for-ad-networks h_01HZ4PBGAG9R9JMHPXVQC1GX3V=troubleshooting-traits-and-limitations h_01HZ2859J5P6MFKACKBK46J6GP=error-messages-and-solutions h_01HZ27W0409NF4Y6RNT8WPW8HP=traits-and-limitations h_01KZ8QYNGH1Q6QXQDC14QG96FZ=see-also" />
