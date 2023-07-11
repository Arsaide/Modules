# Project Files
Files from projects "Practical Java Script"

# Eng description
Here will be published various module files from the projects I completed in Ivan Petrichenko's "Practical Java Script" course.

JS-UI library files will also be published.

# UA description
Тут будуть опубліковані різні файли модулів з проектів, які я пройшов на курсі Івана Петриченка "Практичний Java Script".

Також буде опубліковані файли JS-UI бібліотеки.

# Library Documentation

## 1. HTML - компоненты

<details>
<summary>CARD</summary>

** *class* ** - не обязательные классы

HTML:

    <div class="NAME-WRAPPER d-flex *f-space-around*">
        <div class="card">
            <img class="card-img" src="SRC" alt="PHOTO">
            <div class="card-body">
                <div class="card-title">#Card-title</div>
                <p class="card-text">Lorem ipsum</p>
                <a href="#" class="btn *btn-primary*">LINK</a>

                <!-- Для модального окна вызова -->
                <a href="#" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">Link to</a>   
                
            </div>
        </div>
    </div>

</details>
<details>
<summary>#MODAL WINDOW: (/sass/)</summary>

** *class* ** - не обязательные классы

data-close - дата атрибут при нажатии на который закрывается модальное окно


data-target -  уникальный id для инициализации модального окна

data-toggle - обязательные класс модального окна

HTML - триггер для вызова модального окна:

*Может быть любым блоком! <button>, <div>, <a>*

    <a href="#" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">Link to</a>

HTML - карточки: 

    <div class="modal" id="exampleModal">
        <div class="modal-dialog">
            <div class="modal-content">
                <button class="close" data-close>
                    <span>&times;</span> <!-- Крестик -->
                </button>
                <div class="modal-header">
                    <div class="modal-title">#TITLE</div>
                </div>
                <div class="modal-body">#TEXT</div>
                <div class="modal-footer">
                    *<button class="btn *btn-danger*" data-close>Close</button>*
                    *<button class="btn *btn-success*">Save changes</button>*
                </div>
            </div>
        </div>
    </div>

</details>


<details>
<summary>DYNAMIC MODAL WINDOW</summary>

JS code:

    $('#trigger').click(() => $('#trigger').createModal({ // #trigger - уникальный индифакатор кнопки запуска модального окна
        text: {
            title: 'Modal title',   // заголовок кнопки
            body: 'Lorem ipsum...'  // текст, содержимое кнопки
        },
        btns: {
            count: 3,
            settings: [
                [
                    'Name button',
                    ['btn-danger', 'mr-10'],    // Классы кнопок
                    true    // Добавления атрибута data-close
                ],
                [
                    'Name button',
                    ['btn-success'],    // Классы кнопок
                    false,  // Добавления атрибута data-close
                    () => {
                        alert('Данные сохранены');
                    }   // callback функция при нажатии на кнопку
                ],
            ]
        }
    }));

</details>
