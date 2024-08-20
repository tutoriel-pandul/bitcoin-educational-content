---
term: BIP8
---

Разработанный после дебатов по поводу SegWit, который использовал BIP9 для своей активации, BIP8 представляет собой метод активации мягкого форка, который изначально включает в себя автоматический механизм UASF (*User-Activated Soft Fork* - Мягкий форк, активируемый пользователями). Как и BIP9, BIP8 использует сигнализацию майнеров, но добавляет параметр `LOT` (*Lock-in On Time out* - Блокировка по истечении времени). Если `LOT` установлен в `true`, по истечении периода сигнализации без достижения необходимого порога, автоматически запускается UASF, принудительно активируя мягкий форк. Этот подход заставляет майнеров сотрудничать или рисковать тем, что UASF будет наложен пользователями. Более того, в отличие от BIP9, BIP8 определяет период сигнализации на основе высоты блока, исключая потенциальные манипуляции с хешрейтом со стороны майнеров. BIP8 также позволяет устанавливать переменный порог голосования и вводит параметр для минимальной высоты блока для активации, давая майнерам время подготовиться и заранее сигнализировать о своем согласии, не обязательно будучи готовыми. Когда мягкий форк активируется через BIP8 с параметром `LOT=true`, это использует очень агрессивный метод в отношении майнеров, которые сразу оказываются под давлением потенциального UASF. Фактически, это оставляет им только 2 варианта:
* Быть сотрудничающими и таким образом облегчить процесс активации;
* Быть несотрудничающими, в этом случае пользователи автоматически выполняют UASF, чтобы наложить мягкий форк.