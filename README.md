# Training_project_2021

*Встроенные библиотеки*: Pandas, NumPy, Sklearn, Matplotlib, Seaborn и другие; модели Machine Learning для решение задач регрессии и классификации.

***Восстановление золота из руды.***   
*Задача*: Модель должна предсказать коэффициент восстановления золота из золотосодержащей руды; оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками; спрогнозировать эффективность обогащения чернового концентрата и финального (задача регрессии).  
*Данные и фичи*: данные с параметрами добычи и очистки. Целевой признак: эффективность обогащения чернового концентрата rougher.output.recovery, эффективность обогащения финального концентрата final.output.recovery.  
*Стек инструментов*: Готовые выборки без необходимости train_test_split и восстановление части признаков из полного датафрейма, сопоставление распределений по обучающей и тестовой выборкам, концентрации веществ на разных стадиях.
Применение cross_val_score, StandardScaler, SimpleImputer, make_pipeline. Вычислены sMAPE и final_sMAPE для проверки лучшей модели на train и test.  
*Результаты*: Данный проект прежде всего был сложен пониманием технологического процесса. С помощью кросс-валидации выбрана лучшая модель (по меньшей ошибке sMAPE)- LinearRegression.   
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%92%D0%BE%D1%81%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%B7%D0%BE%D0%BB%D0%BE%D1%82%D0%B0.ipynb  

***Выбор тарифа.***  
*Задача*: Исходя из анализа поведения клиентов сделать вывод какой тариф приносит больше денег компании для планирования рекламного бюджета.  
*Данные и фичи*: характеристики тарифов (Смарт и Ультра) на услуги мобильной связи.   
*Cтек инструментов*: Подробно разобрана тема по join-ам и проверка гипотез по p_value.   
*Результаты*: При проверке гипотез по p_value выявлены следующие моменты (если принять допущение, что вся база абонентов, как и выборка неравномерна по видам тарифных планов!), то перспективным следует считать тариф Смарт с меньшей абонентской платой, где стабильно идут доплаты за услуги при примерно одинаковом доходе от абонентов Москвы и регионов.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%92%D1%8B%D0%B1%D0%BE%D1%80%20%D1%82%D0%B0%D1%80%D0%B8%D1%84%D0%B0.ipynb

***Определение стоимости автомобиля.***  
*Задача*: Построить модель для определения стоимости автомобиля (задача регрессии).   
*Данные и фичи*: технические характеристики, комплектации и цены автомобилей. Целевой признак: Price — цена(евро).  
*Стек инструментов*: Применены time, train_test_split, GridSearchCV, cross_val_score, StandardScaler, OrdinalEncoder, mean_squared_error и новая модель LGBMRegressor.  
*Результаты*: Важно соблюдение качества и скорости предсказания, времени обучения. Выбор лучшей модели по метрике RMSE- в лидерах оказалась изученная модель LGBMRegressor, сокращающая ошибку прогнозирования в 2 раза в сравнении с другими рассмотренными моделями при увеличенном времени на обучение/ предсказание.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5%20%D1%81%D1%82%D0%BE%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D0%B8%20%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D0%B5%D0%B9.ipynb

***Отток клиентов из банка.***  
*Задача*: Построить модель для прогноза уйдет ли клиент из банка в ближайшее время (задача классификации).  
*Данные и фичи*: характеристики клиентов банка. Целевой признак: Exited — факт ухода клиента.  
*Стек инструментов*: train_test_split, StandardScaler, shuffle, accuracy_score, f1_score, precision_recall_curve, roc_curve, confusion_matrix, classification_report. Проект с применением техник масштабирования и стандартизации, методов борьбы с дисбалансом классов (upsample, downsample).  
*Результаты*: Выбрана лучшая модель RandomForestClassifier, показавшая положительную динамику на PR-кривой и roc_auc_score= 0.87 ( при F1 = 0.63- превышающая минимально обозначенное значение метрики по условию в 0.59).  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9E%D1%82%D1%82%D0%BE%D0%BA%20%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%BE%D0%B2.ipynb

***Поиск токсичных комментариев.***   
*Задача*: Обучение модели классификации комментариев на позитивные и негативные (задача классификации).  
*Данные и фичи*: набор данных с разметкой о токсичности комментариев. Целевой признак: 'toxic'.  
*Стек инструментов*: Применение train_test_split, shuffle, f1_score, confusion_matrix, time и специфичные метрики- TfidfVectorizer, stopwords.    
*Результаты*: Данные с помощью upsampled сбалансированы по классам, очищены и лематизированы комментарии, применены stopwords и TF-IDF. Получены эмбендинги на предобученной модели BERT и обучение/ предсказание по LogisticRegression()с F1_test >0.75.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9F%D0%BE%D0%B8%D1%81%D0%BA%20%D1%82%D0%BE%D0%BA%D1%81%D0%B8%D1%87%D0%BD%D1%8B%D1%85%20%D0%BA%D0%BE%D0%BC%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%80%D0%B8%D0%B5%D0%B2.ipynb

***Предсказание скважины.***  
*Задача*: Построить модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль (задача регрессии).     
*Данные и фичи*: характеристики скважин и регионов их прогнозирования. Целевой признак- product.  
*Стек инструментов*: Применение train_test_split, RandomState. Проверка корреляции признаков sns.heatmap в рамках каждого региона, обучение/предсказание и масштабирование данных StandardScaler, расчет метрик R_2, MAE, RMSE.  
*Результаты*: Техникой Bootstrap, формируя подвыборки определены лучшие предсказания прибыли и рисков- 'region 1'. Соблюдена вероятность риска убытков <2,5% (95%-й доверительный интервал при риске убытков 0.3%).  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9F%D1%80%D0%B5%D0%B4%D1%81%D0%BA%D0%B0%D0%B7%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%81%D0%BA%D0%B2%D0%B0%D0%B6%D0%B8%D0%BD%D1%8B.ipynb

***Прогнозирование такси.***  
*Задача*: Построить модель для прогноза количества заказов такси на следующий час (задача регрессии).  
*Данные и фичи*: данные о заказах такси в аэропортах. Целевой признак- 'num_orders' («число заказов»).  
*Стек инструментов*: Применение train_test_split с подбором параметров по GridSearchCV, mean_squared_error, time и новые специфичные метрики - seasonal_decompose, TimeSeriesSplit.    
*Результаты*: Выполнен ресемплинг за час; разложен временной ряда на тренд, сезонную составляющую, остаток декомпозиции; дополнительно декомпозиция данных в рамках недели, суток. Наблюдается явный тренд, сезонность, разброс дисперсии (ряд нестационарный). Для обучения/ предсказания определены составляющие: max_lag, rolling_mean_size.
Лучшая модель LGBMRegressor с RMSE- 41.8 (ограничение метрики <48), ее стоит рекомендовать для предсказания количества заказов на следующий час.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%B7%D0%B0%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2%20%D1%82%D0%B0%D0%BA%D1%81%D0%B8.ipynb

***Продажа квартир.***  
*Задача*: Установить параметры определения рыночной стоимости объектов недвижимости на основании которых далее будет построена автоматизированная система для отслеживания аномалий и мошеннической деятельности.       
*Данные и фичи*: характеристики квартир на продажу (указанные пользователями, полученные автоматически по картографическим данным).    
*Стек инструментов*: В данном проекте предстояло детально проработать срезы (.query), оценить корреляцию факторов влияющих на стоимость квартиры и сопоставить получившиеся данные с логикой реального положения дел на рынке недвижимости Санкт-Петербурга.    
*Результаты*: выявлен ряд аномалий (в ценах, метрах, сутках размещения объявления в системе) при четко верных закономерностях квартиры бОльшей площади обычно в центре с высокими потолками, на последних этажах и приближенные к центру города стоят значительно дороже за редким исключением касающихся объектов элитного пригорода.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9F%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B0%20%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80.ipynb

***Продажа компьютерных игр.***  
*Задача*: Выявить определяющие успешность игры закономерности для планирования рекламных акций.  
*Данные и фичи*: характеристики компьютерных игр.  
*Стек инструментов*: Здесь главный акцент на сводные таблицы (.pivot_table), построение гистограмм с помощью цикла и проверка гипотез, по sns.heatmap отражение корреляции признаков.    
*Результаты*: В быстроменяющейся индустрии компьютерных игр были определены следующие тренды- игры в стадии роста PC4, XOne сохранят его в ближайшие годы (регион Европа и Северная Америка), относительно жанра это action и прибыльный shooter; менталитет Японии и здесь показывает индивидуальную оценку прогноза.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%9F%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B0%20%D0%BA%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D1%8B%D1%85%20%D0%B8%D0%B3%D1%80.ipynb

***Рекомендация тарифа.***  
*Задача*: Построить модель, которая выберет подходящий тариф исходя из данных о поведении клиентов, которые уже перешли на эти тарифы (задача классификации).     
*Данные и фичи*: характеристики тарифа (Ультра-1, Смарт-0). Целевой признак- 'is_ultra'.  
*Стек инструментов*: Отработана тема train_test_split с подбором гиперпараметров по GridSearchCV и проведение проверки на адекватность выбранной модели, расчет метрики accuracy_score.  
*Результаты*: Выбрана модель RandomForestClassifier с accuracy 0.78 на тесте, превышающая минимально допустимую метрику в 0.75 (в т.ч. модель превзошла DummyClassifier).  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%A0%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D1%8F%20%D1%82%D0%B0%D1%80%D0%B8%D1%84%D0%B0.ipynb

***Скоринговая модель.***  
*Задача*: Построить модель кредитного скоринга (специальной системы, которая оценивает способность потенциального заёмщика вернуть кредит банку).   
*Данные и фичи*: характеристики потенциального заемщика.  
*Стек инструментов*: Отработана тема лематизации и категоризация данных. Расчет .groupby для формирования выборок в соответствии с запросами проекта.    
*Результаты*: Сформированы и подтверждены расчетами ряд вопросов относительно потенциальных заемщиков- наблюдается зависимость между наличием детей, семейным положением, целями кредита и вероятностью возврата кредита в срок.  
*Проект*: https://github.com/k-vero2021/Training_project_2021/blob/main/%D0%A1%D0%BA%D0%BE%D1%80%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%B0%D1%8F%20%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8C.ipynb
