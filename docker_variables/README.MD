Опытным путем пришел к тому, что:
1. ARG работает только на этапе сборки.
2. ARG для определения достаточно указать ARG MY_VARIABLE_1
3. ARG что бы определить значение по умолчанию можно записать ARG MY_VARIABLE_1="Default ARG" если в compose не задать значение MY_VARIABLE_1, то напечатает "Default ARG"

4. ENV работает только на этапе выполнения контейнера (run stage)
5. ARG и ENV вроде схожие объекты, но ENV в Dockerfile нужно записывать с присвоением:
ENV MY_VARIABLE_4=${MY_VARIABLE_4}

6. Касательно того как присваивать значения в docker compose

6.1. Объявляешь переменную в environment, а значение определяешь в .env, при этом не обяхательно объявлять env_file

6.2. Если прописываешь env_file с именем отличным от .env, например env_file: "example.env", то переменную уже нельзя объявлять в environment, иначе она не приедет в dockerfile.

Картинка для понимания: docker_variables/img.jpg
