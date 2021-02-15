---
title: Gestire l'app Complimento nell'interfaccia di amministrazione di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: adotey
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Informazioni sulle impostazioni di amministrazione nell'app Complimento nell'interfaccia di amministrazione di Microsoft Teams
ms.openlocfilehash: acb9d000aeec61daa35421c5ded389888032873f
ms.sourcegitcommit: d2e67f2eed7b817c2c5f76015ec11582d0e0cb9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "50037852"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l'app Complimento nell'interfaccia di amministrazione di Microsoft Teams

> [!NOTE]
> Gli amministratori devono avere una licenza di Teams per accedere a questa funzionalità. Se provi ad accedere a questa funzione senza una licenza di Teams, verrà visualizzato un messaggio di errore.

L'app Complimento in Microsoft Teams consente agli utenti di mostrare il proprio apprezzamento ai membri dell'organizzazione o della classe. Con una selezione di set di badge tra cui scegliere e l'opzione per creare badge personalizzati, Complimento è progettato per aiutare a riconoscere l'impegno che viene inserito nell'ampia gamma di lavori degli utenti di Teams, dai docenti agli operatori in prima linea. Per altre informazioni, vedere [Inviare un complimento alle persone.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Gli amministratori possono controllare quali badge sono disponibili per l'organizzazione dall'interfaccia di amministrazione di Microsoft Teams. Nella barra di spostamento sinistra, vai alle **app di Teams > Gestisci app.** Nell'elenco delle app fare **clic** su Complimento e quindi selezionare **Impostazioni.**  Da qui è possibile scegliere di abilitare i set di badge predefiniti e predefiniti e creare badge personalizzati.

![Screenshot della scheda Impostazioni per l'app Complimento](media/manage-praise-app-settings.png)

> [!NOTE]
> L'app Complimento non è disponibile per le nuvole governative degli Stati Uniti.

## <a name="use-built-in-badge-sets"></a>Usare set di badge predefiniti

I set predefiniti sono raccolte di badge progettati da Microsoft per l'app Complimento. Questi set non sono modificabili dagli amministratori. Il set di badge predefinito è già abilitato e disponibile nell'app Complimento. Per modificare la disponibilità del set predefinito o di qualsiasi set di badge, attivare o disattivare l'interruttore corrispondente. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Badge predefiniti

Il set di badge predefinito è progettato per aiutare gli utenti di Teams a riconoscere i colleghi per andare oltre e oltre con il proprio lavoro.

![Anteprima del set di badge predefinito](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Badge di apprendimento sociale ed emotivo per l'istruzione

I docenti possono riconoscere i singoli studenti per i risultati e i comportamenti di apprendimento sociale ed emotivo (SEL) con badge che illustrano questi concetti.

![Anteprima dei badge di apprendimento sociale ed emotivo per l'istruzione](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Creare badge personalizzati

Selezionare **Crea un badge personalizzato.** Da qui è possibile progettare un badge personalizzato nel riquadro laterale. È possibile creare fino a 25 badge personalizzati. 

![Screenshot del riquadro Crea un badge personalizzato](media/manage-praise-app-create-custom-badge.png)

1. Immettere un nome di badge. Nome visualizzato nel badge quando gli utenti inviano un complimento.

2. Impostare i colori del badge. Per impostare i colori del testo e dello sfondo del badge, è necessario immettere i colori come valori esadecimali (esadecimali).

   > [!TIP]
   > Se non si ha distogliere [](#hex-colors-intro) i valori esadecimali, questo articolo include una rapida introduzione per illustrarne l'uso.

3. Caricare un'immagine badge. Il tipo di file accettato è . PNG. Il file di immagine deve essere inferiore a 40 KB con dimensioni massime di 216 X 216 pixel.
![Badge con campi di sfondo, testo e immagine etichettati](media/praise-app-badge-fields.png)

4. Localizzare il nome della notifica: in **Nomi badge localizzati** selezionare **Aggiungi.** Selezionare le impostazioni locali desiderate nell'elenco a discesa. Immettere quindi il nome del badge nella lingua designata.

5. Escludere il badge da impostazioni locali specifiche: in **Escludi badge da** queste impostazioni locali selezionare **Aggiungi.** Selezionare le impostazioni locali da escludere dall'elenco a discesa.

6. Selezionare **Applica.** Il nuovo badge verrà visualizzato nella tabella dei badge personalizzati.

> [!NOTE]
> Se i passaggi 4 e 5 vengono ignorati, il badge verrà visualizzato nella lingua predefinita per tutte le impostazioni locali.
>
> Dopo aver apportato tutte le modifiche alla selezione del badge, assicurarsi di selezionare **Invia.** Possono essere necessarie alcune ore prima che le modifiche siano disponibili per l'organizzazione.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Specificare colori con valori esadecimali

I valori esadecimali sono stringhe di sei cifre esadecimali che rappresentano l'intensità di rosso (RR), verde (GG) e blu (BB) in un colore specifico su una scala da 00 a FF. Quando si uniscono i valori di tutti e tre i colori, si ottiene un valore esadecimale: #RRGGBB

Ad esempio, il valore esadecimale per il colore rosso è #FF0000 perché il rosso è impostato sul valore più alto possibile, FF e il verde e il blu sono impostati sul valore più basso possibile, 00.

Per esplorare colori e valori esadecimali diversi, vedere selezione colori [di Bing.](https://www.bing.com/search?q=color+picker)

Di seguito è riportato un elenco di colori di esempio per iniziare:

|Colore  |Valore esadecimale|
|-------|---------|
|![colore esadecimale #FF6666](media/hexColor1.png)|  #FF6666   |
|![colore esadecimale #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![colore esadecimale #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![colore esadecimale #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![colore esadecimale #800080](media/hexColor5.png)|  #800080   |
|![colore esadecimale #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Procedure consigliate per la creazione di badge personalizzati

**Invia tutti i badge contemporaneamente.** Poiché l'elaborazione dei nuovi badge richiede del tempo, è meglio aggiungere tutti i badge personalizzati alla tabella prima di inviarli.

**Quando si scelgono i colori, tenere presente l'accessibilità.** Alcuni colori si uniscono meglio di altri.  Creare un contrasto tra il testo e i colori di sfondo per semplificare la lettura del nome del badge. Ad esempio, se si sceglie un colore di sfondo scuro, scegliere un colore chiaro per il testo.

**Quando si seleziona un'immagine, tenere presenti le dimensioni del badge.** Per una qualità ottimale, è consigliabile caricare un file di immagine di dimensioni 216 x 216 pixel (ovvero le dimensioni massime). Evitare di estendere o distorcere l'immagine per adattarla a queste dimensioni.

**Se l'immagine del badge non è rettangolare, renderla trasparente.** Sarà necessario eseguire questa operazione prima di caricare il file di immagine in Complimento.

![Sinistra: badge con immagine non trasparente, destra: badge con immagine trasparente](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Badge set assets

I set di badge predefiniti non possono essere modificati, quindi quando un set predefinito è abilitato, tutti i badge del set vengono aggiunti all'app Complimento. Se vuoi aggiungere badge specifici da un set predefinito e oscenirne altri, crea di nuovo i badge che vuoi usare come badge personalizzati. È possibile scaricare l'immagine del badge e trovare il testo e i colori di sfondo dei badge dei set predefiniti nelle tabelle seguenti.

### <a name="default-badges-assets"></a>Risorse badge predefinite

</br>

|Nome badge     |File di immagine  |Colore del testo | Colore di sfondo |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Straordinario        |[PNG straordinario](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Allenatore          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Invasa        |[PNG conse erta](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Creative       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inclusivo      |[PNG inclusivo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Cuore gentile     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Leadership     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Snodato       |[PNG semestio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Risolutore di problemi |[PNG risolutore di problemi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Giocatore del team    |[PNG del lettore di team](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Grazie      |[Grazie PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Badge di apprendimento sociale ed emotivo per i beni didattici

</br>

|Nome badge        |File di immagine  |Colore del testo | Colore di sfondo |
|------------------|------------|---------- |--------|
|Comunicazione     |[Communication PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Pensiero critico |[PNG con pensiero critico](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Invasi         |[PNG snodato](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empatia           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Obiettivo principale      |[Obiettivo PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivazione        |[PNG motivazione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenza       |[PNG persistenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Rispetta           |[Rispetta PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Responsabilità    |[Responsibility PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Auto consapevolezza    |[PNG auto consapevolezza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Gestione in autonomia   |[PNG di auto-gestione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Pensieroso    |[Pensieroso PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
