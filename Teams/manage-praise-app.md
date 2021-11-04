---
title: Gestire l'app Complimenti nell'interfaccia Teams di amministrazione
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: jozhuan
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Informazioni sulle impostazioni di amministrazione nell'app Complimenti nell'interfaccia Microsoft Teams di amministrazione
ms.openlocfilehash: a65fae76440a520e4ed0054f9ac039e417c0e60e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763054"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l Complimenti app nell'interfaccia Microsoft Teams di amministrazione

> [!NOTE]
> Gli amministratori devono avere una licenza Teams per accedere a questa funzionalità. Se si prova ad accedere a questa funzionalità senza Teams licenza, viene visualizzato un messaggio di errore.

L Complimenti app in Microsoft Teams consente agli utenti di mostrare apprezzamento ai membri dell'organizzazione o della classe. Con una selezione di set di badge tra cui scegliere e l'opzione per creare i propri badge, Complimenti è progettato per aiutare a riconoscere l'impegno che si fa nell'ampia gamma di attività che gli utenti Teams eserviranno, dai docenti ai lavoratori in prima linea. Per altre informazioni, vedere [Inviare Complimenti alle persone](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Gli amministratori possono controllare quali badge sono disponibili per l'organizzazione dall'Microsoft Teams di amministrazione. Nel riquadro di spostamento sinistro passare a Teams **app > Gestisci app**. Nell'elenco delle app fare clic su **Complimenti** e quindi selezionare **Impostazioni**.  Da qui è possibile scegliere di abilitare i set di badge predefiniti e predefiniti e creare badge personalizzati.

![Screenshot della Impostazioni per l'app Complimenti.](media/manage-praise-app-settings.png)

> [!NOTE]
> La Complimenti dell'app non è disponibile per i cloud governativi degli Stati Uniti.

## <a name="use-built-in-badge-sets"></a>Usare set di badge predefiniti

I set predefiniti sono raccolte di badge progettati da Microsoft per l Complimenti app. Questi set non sono modificabili dagli amministratori. Il set di badge predefinito è già abilitato e disponibile nell'app Complimenti predefinita. Per modificare la disponibilità del set predefinito o di qualsiasi set di badge, impostare l'interruttore corrispondente su Attivato o Disattivato. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Badge predefiniti

Il set di badge predefinito è progettato per aiutare Teams gli utenti a riconoscere i colleghi per andare oltre con il proprio lavoro.

![Anteprima del set di badge predefinito.](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Badge di apprendimento sociale ed emotivo per l'istruzione

I docenti possono riconoscere singoli studenti per obiettivi e comportamenti di apprendimento sociale ed emotivo (SEL) con badge che illustrano questi concetti.

![Anteprima dei badge di apprendimento sociale ed emotivo per l'istruzione.](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Creare badge personalizzati

Selezionare **Crea un badge personalizzato.** Da qui è possibile progettare un badge personalizzato nel riquadro laterale. È possibile creare fino a 25 badge personalizzati. 

![Screenshot del riquadro Crea un badge personalizzato.](media/manage-praise-app-create-custom-badge.png)

1. Immettere un nome di badge. Questo è il nome che verrà visualizzato nel badge quando gli utenti inviano complimenti.

2. Impostare i colori del badge. Per impostare i colori del testo e dello sfondo del badge, è necessario immettere i colori come valori esadecimali (esadecimali).

   > [!TIP]
   > Se non si ha novità per i valori esadecimali, questo articolo include una rapida [introduzione](#hex-colors-intro) per illustrare come usarli.

3. Upload'immagine di un badge. Il tipo di file accettato è .PNG. Il file di immagine deve essere inferiore a 40 KB con dimensioni massime di 216 x 216 pixel.
![Badge con campi di sfondo, testo e immagine etichettati.](media/praise-app-badge-fields.png)

4. Localizzare il nome del badge: in **Nomi badge localizzati** selezionare **Aggiungi.** Selezionare le impostazioni locali desiderate nell'elenco a discesa. Immettere quindi il nome del badge nella lingua designata.

5. Escludere il badge da impostazioni locali specifiche: in **Escludi badge da queste impostazioni** locali selezionare **Aggiungi**. Selezionare le impostazioni locali da escludere dall'elenco a discesa.

6. Selezionare **Applica**. Il nuovo badge verrà ora visualizzato nella tabella dei badge personalizzati.

> [!NOTE]
> Se i passaggi 4 e 5 vengono ignorati, il badge sarà nella lingua predefinita per tutte le impostazioni locali.
>
> Dopo aver apportato le modifiche alla selezione del badge, assicurarsi di selezionare **Invia.** Potrebbero essere necessarie fino a poche ore prima che queste modifiche siano disponibili per l'organizzazione.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Specificare i colori con valori esadecimali

I valori dei colori esadecimali sono stringhe di sei cifre esadecimali che rappresentano l'intensità del rosso (RR), del verde (GG) e del blu (BB) in un colore specifico su una scala da 00 a FF. Quando si uniscono i valori di tutti e tre i colori, si ottiene un valore esadecimale: #RRGGBB

Ad esempio, il valore esadecimale per il colore rosso è #FF0000 perché il rosso è impostato sul valore più alto possibile, FF e verde e blu sono impostati al valore più basso possibile, 00.

Per esplorare colori diversi e i relativi valori esadecimali, vedere Bing [selezione colori.](https://www.bing.com/search?q=color+picker)

Di seguito è riportato un elenco di colori di esempio per iniziare:

|Colore  |Valore esadecimale|
|-------|---------|
|![colore esadecimale #FF6666.](media/hexColor1.png)|  #FF6666   |
|![colore esadecimale #7FFFD4.](media/hexColor2.png)|  #7FFFD4   |
|![colore esadecimale #FF75F0.](media/hexColor3.png)|  #FF75F0   |
|![colore esadecimale #00BFFF.](media/hexColor4.png)|  #00BFFF   |
|![colore esadecimale #800080.](media/hexColor5.png)|  #800080   |
|![colore esadecimale #0000000.](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Procedure consigliate per la creazione di badge personalizzati

**Invia tutti i tuoi badge contemporaneamente.** Poiché l'elaborazione dei nuovi badge richiede del tempo, è meglio aggiungere tutti i badge personalizzati alla tabella prima di inviarli.

**Quando si scelgono i colori, tenere presente l'accessibilità.** Alcuni colori si uniscono meglio di altri.  Creare un contrasto tra il testo e i colori di sfondo per semplificare la lettura del nome del badge. Ad esempio, se si sceglie un colore di sfondo scuro, scegliere un colore di testo chiaro.

**Quando si seleziona un'immagine, tenere presente le dimensioni del badge.** Per una qualità ottimale, è consigliabile caricare un file di immagine di 216 x 216 pixel,ovvero le dimensioni massime. Evitare di allungare o distorcere l'immagine per adattarla a queste dimensioni.

**Se l'immagine del badge non è rettangolare, rendere trasparente l'immagine.** È necessario eseguire questa operazione prima di caricare il file di immagine in Complimenti.

![A sinistra: badge con immagine non trasparente, a destra: badge con immagine trasparente.](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Risorse del set di badge

I set di badge predefiniti non possono essere modificati, quindi quando è abilitato un set predefinito, tutti i badge nel set vengono aggiunti all'app Complimenti predefinita. Se si vogliono aggiungere badge specifici da un set predefinito e osare altri utenti, creare di nuovo i badge da usare come badge personalizzati. È possibile scaricare l'immagine del badge e trovare il testo e i colori di sfondo dei badge dai set predefiniti nelle tabelle seguenti.

### <a name="default-badges-assets"></a>Risorse badge predefinite

</br>

|Nome del badge     |File di immagine  |Colore del testo | Colore di sfondo |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Eccezionale        |[PNG straordinario](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Coach          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Coraggio        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Creatività       |[PNG creativo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inclusivo      |[PNG inclusivo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Cuore gentile     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Leadership     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Ottimismo       |[Ottimizza PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Risolutore di problemi |[PNG risolutore di problemi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Giocatore del team    |[PNG del giocatore del team](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Grazie      |[Grazie PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Badge di apprendimento sociale ed emotivo per le risorse didattiche

</br>

|Nome del badge        |File di immagine  |Colore del testo | Colore di sfondo |
|------------------|------------|---------- |--------|
|Comunicazione     |[PNG di comunicazione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Pensiero critico |[PNG pensiero critico](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosità         |[Curiosity PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empatia           |[PNG empatia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Ricerca degli obiettivi      |[Obiettivo ricerca PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivazione        |[Motivazione PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenza       |[PNG di persistenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Rispetto           |[Rispetta PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Responsabilità    |[PNG di responsabilità](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Consapevolezza di sé    |[PNG di autosassazione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Gestione autonoma   |[PNG auto-gestione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Premura    |[PNG riflessivo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
