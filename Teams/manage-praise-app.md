---
title: Gestire l'app elogi nell'interfaccia di amministrazione di Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Informazioni sulle impostazioni di amministrazione nell'app elogi nell'interfaccia di amministrazione di Microsoft Teams
ms.openlocfilehash: 2fa2f7e92646dafe3d8bf1cc39325a682c823686
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656307"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l'app elogi nell'interfaccia di amministrazione di Microsoft Teams

L'app elogi in Microsoft teams consente agli utenti di mostrare apprezzamento ai membri della propria organizzazione o classe. Con una selezione di set di badge tra cui scegliere e la possibilità di creare badge personalizzati, l'elogio è progettato per aiutare a riconoscere lo sforzo che entra nell'ampia gamma di lavoro che fanno gli utenti dei team, dagli insegnanti ai lavoratori di prima linea.

Gli amministratori possono controllare quali badge sono disponibili per la propria organizzazione dall'interfaccia di amministrazione di teams. Nella barra di spostamento sinistra, seleziona **app teams > Gestisci app**. Aprire elogi nel [catalogo dell'app tenant](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)e scegliere **Impostazioni**.

## <a name="use-built-in-badge-sets"></a>Usare set di badge predefiniti

I set predefiniti sono insiemi di badge progettati da Microsoft per l'app elogi. Questi set non sono modificabili dagli amministratori. Il set di badge predefinito è già abilitato e disponibile nell'app elogi. Per modificare la disponibilità del set predefinito o dei set di badge, cambiare l'interruttore corrispondente su attivato o disattivato. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Badge predefiniti

Il set di badge predefinito è progettato per aiutare gli utenti del team a riconoscere i loro coetanei per andare al di là del loro lavoro.

![Anteprima del set di badge predefinito](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Badge per l'apprendimento sociale ed emotivo per l'istruzione

Gli insegnanti possono riconoscere i singoli studenti per ottenere risultati e comportamenti di apprendimento sociale ed emotivo (SEL) con badge che illustrano questi concetti.

![Anteprima dei badge di apprendimento sociale ed emotivo per l'istruzione](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Creare badge personalizzati

Passare i **badge personalizzati** su attivato e selezionare **Crea un badge personalizzato**. Da lì è possibile progettare un badge personalizzato nel pannello laterale. Puoi creare fino a 25 badge personalizzati. 

1. Immettere un nome per il badge. Questo è il nome che verrà visualizzato nel badge quando gli utenti inviano elogi.

2. Impostare i colori del badge. Per impostare il testo e i colori di sfondo del badge, è necessario immettere i colori come valori esadecimali.

   > [!TIP]
   > Se non si ha familiarità con i valori esadecimali, questo articolo include una [rapida introduzione](#hex-colors-intro) per illustrare come usarli.

3. Caricare un'immagine di badge. Il tipo di file accettato è. PNG. Il file di immagine deve essere inferiore a 40 KB con dimensioni massime di 216 X 216 pixel.
![Badge con campi in background, testo e immagini etichettati](media/praise-app-badge-fields.png)

4. Localizzare il nome del badge: in **nomi di badge localizzati**selezionare **Aggiungi**. Selezionare le impostazioni locali desiderate nell'elenco a discesa. Immettere quindi il nome del badge nella lingua designata.

5. Escludere il badge da impostazioni locali specifiche: in **Escludi badge da queste impostazioni locali**selezionare **Aggiungi**. Selezionare le impostazioni locali che si desidera escludere dall'elenco a discesa.

6. Selezionare **applica**. Il nuovo badge verrà ora visualizzato nella tabella badge personalizzati.

> [!NOTE]
> Se i passaggi 4 e 5 vengono ignorati, il badge sarà nella lingua predefinita per tutte le impostazioni locali.
>
> Dopo aver apportato le modifiche alla selezione del badge, assicurati di selezionare **Invia**. Potrebbero essere necessarie fino a poche ore prima che le modifiche siano disponibili per l'organizzazione.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Specificare i colori con valori esadecimali

I valori di colore esadecimale sono stringhe di sei cifre esadecimali che rappresentano l'intensità di rosso (RR), verde (GG) e blu (BB) in un colore specifico in una scala da 00 a FF. Quando si inseriscono insieme i valori di tutti e tre i colori, viene ottenuto un valore esadecimale: #RRGGBB

Ad esempio, il valore esadecimale per il colore rosso è #FF0000 perché il rosso è impostato al valore massimo possibile, FF e verde e blu sono impostati al valore più basso possibile, 00.

Per esplorare i diversi colori e i relativi valori esadecimali, consulta [selezione colori di Bing](https://www.bing.com/search?q=color+picker).

Di seguito è riportato un elenco di colori di esempio per iniziare:

|Colore  |Valore esadecimale|
|-------|---------|
|![#FF6666 di colore esadecimale](media/hexColor1.png)|  #FF6666   |
|![#7FFFD4 di colore esadecimale](media/hexColor2.png)|  #7FFFD4   |
|![#FF75F0 di colore esadecimale](media/hexColor3.png)|  #FF75F0   |
|![#00BFFF di colore esadecimale](media/hexColor4.png)|  #00BFFF   |
|![#800080 di colore esadecimale](media/hexColor5.png)|  #800080   |
|![#000000 di colore esadecimale](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Procedure consigliate per la creazione di badge personalizzati

**Inviare tutti i badge contemporaneamente.** Dato che occorre un po' di tempo per l'elaborazione di nuovi badge, è consigliabile aggiungere tutti i badge personalizzati alla tabella prima di inviarli.

**Quando si scelgono i colori, tieni presente l'accessibilità.** Alcuni colori vanno insieme meglio di altri.  Creare un contrasto tra il testo e i colori di sfondo per semplificare la lettura del nome del badge. Se ad esempio si sceglie un colore di sfondo scuro, scegliere un colore di testo chiaro.

**Quando si seleziona un'immagine, tieni presente la dimensione del badge.** Per ottenere una qualità ottimale, è consigliabile caricare un file di immagine di 216 x 216 pixel (che rappresentano le dimensioni massime). Evitare di allungare o distorcere l'immagine per adattarla a queste dimensioni.

**Se l'immagine del badge non è rettangolare, rendere trasparente l'immagine.** È necessario eseguire questa operazione prima di caricare il file di immagine in elogio.

![A sinistra: badge con immagine non trasparente, a destra: badge con immagine trasparente](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Asset set di badge

I set di badge predefiniti non possono essere modificati, quindi quando un set predefinito è abilitato, tutti i badge del set vengono aggiunti all'app elogio. Se si desidera aggiungere badge specifici da un set predefinito e ometterne altri, ricreare i badge che si desidera utilizzare come badge personalizzati. È possibile scaricare l'immagine del badge e trovare il testo e i colori di sfondo dei badge dagli insiemi predefiniti nelle tabelle seguenti.

### <a name="default-badges-assets"></a>Asset badge predefiniti

</br>

|Nome badge     |File di immagine  |Colore del testo | Colore di sfondo |
|---------------|------------|---------- |--------|
|Achiever       |[PNG per l'ottenimento](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Impressionante        |[PNG awesome](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png>Awesome.PNG)</a>|#8283B2    |#D1EFF2|
|Allenatore          |[PNG in pullman](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Coraggio        |[PNG di Courage](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Creative       |[PNG creativi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inclusive      |[PNG inclusi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Cuore gentile     |[PNG cuore tipo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Leadership     |[PNG leadership](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership.pn)|#419098    |#D2EAEC|
|Ottimismo       |[Ottimismo PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Risolutore di problemi |[PNG Risolutore di problemi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Giocatore del team    |[PNG del team player](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Grazie      |[Grazie PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Badge per l'apprendimento sociale ed emotivo per i beni didattici

</br>

|Nome badge        |File di immagine  |Colore del testo | Colore di sfondo |
|------------------|------------|---------- |--------|
|Comunicazione     |[PNG di comunicazione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Pensiero critico |[Pensiero critico PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosità         |[Curiosità PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empatia           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Ricerca obiettivo      |[PNG Pursuit obiettivo](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivazione        |[PNG motivazione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenza       |[PNG persistenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Rispetto           |[Rispettare il formato PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Responsabilità    |[PNG di responsabilità](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Consapevolezza di sé    |[Self-Awareness PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Gestione automatica   |[PNG di gestione automatica](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Riflessione    |[Riflessione PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
