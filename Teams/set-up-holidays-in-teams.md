---
title: Configurare le festività in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: Informazioni su come configurare le festività in Microsoft teams e connetterle all'operatore automatico usando la caratteristica festività.
ms.openlocfilehash: 531b2ff6c9fedcab7710fbab3ac9bd69d615ab73
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905578"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Configurare le festività in Microsoft Teams

È possibile usare la funzionalità festività di Microsoft teams per pianificare date e orari specifici in cui gli utenti dell'organizzazione deterranno una pausa dal lavoro e non saranno disponibili durante le normali ore lavorative. 

È possibile collegare le festività agli operatori automatici creati all'interno dell'organizzazione. Gli operatori automatici consentono ai chiamanti di spostarsi in un sistema di menu per accedere al reparto giusto o accedere alle informazioni di cui hanno bisogno. Quando si configurano le impostazioni delle chiamate per le festività per un operatore automatico, è possibile selezionare la festività da un elenco, aggiungere un saluto e specificare cosa fare con la chiamata quando viene risolta dall'operatore automatico durante la festività.

Un buon esempio consiste nel creare una festività natalizia per quando molti dei tuoi dipendenti non sono al lavoro. Dopo aver creato gli orari festivi e impostati, è necessario aggiungere la festività all'operatore automatico principale in modo che quando si chiama l'utente si senta un messaggio audio creato. Qualcosa del tipo: "Siamo chiusi per Natale dal 22 dicembre al 27 dicembre. Lasciare un messaggio vocale, in modo da poter restituire la chiamata quando si torna in ufficio.

Per altre informazioni sugli operatori automatici, vedere [che cosa sono gli operatori automatici di cloud](what-are-phone-system-auto-attendants.md)?  

## <a name="create-a-holiday"></a>Creare una festività

1. Nell'interfaccia di amministrazione di Microsoft teams, vai a**vacanze** **Impostazioni** > a livello di organizzazione.

2. Selezionare **nuova festività**.

3. Immettere un nome per la festività.

4. Selezionare **Aggiungi nuova data**.

5. In **ora inizio**selezionare l'icona del calendario e scegliere la data in cui si vuole iniziare la festività.

6. Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.

7. In **fine ora**selezionare l'icona del calendario e scegliere la data in cui si vuole terminare la festività. Se la festività è solo un giorno, questa deve essere la stessa data di quella selezionata in **ora di inizio**.

8. Usare l'elenco a discesa per selezionare un'ora di fine per la festività.

9. Selezionare **Salva**.

## <a name="change-a-holiday"></a>Modificare una festività

1. Nell'interfaccia di amministrazione di Microsoft teams, vai a**vacanze** **Impostazioni** > a livello di organizzazione.

2. Selezionare la festività nell'elenco.

3. In **ora inizio**selezionare l'icona del calendario e scegliere la data in cui si vuole iniziare la festività.

4. Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.

5. In **fine ora**selezionare l'icona del calendario e scegliere la data in cui si vuole terminare la festività. 

6. Usare l'elenco a discesa per selezionare un'ora di fine per la festività.

7. Selezionare **Salva**.

## <a name="connect-a-holiday-to-an-auto-attendant"></a>Connettere una festività a un operatore automatico

1. Nell'interfaccia di amministrazione di Microsoft teams accedere agli**operatori automatici** **vocali** > .
2. Selezionare un account di risorse nell'elenco.
3. Nel riquadro sinistro selezionare **Impostazioni chiamata festività**.
4. Selezionare **nuova festività**.
5. Selezionare la festività nell'elenco a discesa.
6. È possibile aggiungere un messaggio di saluto facoltativo:
    - Per riprodurre un messaggio di saluto registrato, selezionare **Riproduci un file audio**e quindi selezionare **Carica file**. Passare al percorso del file audio, selezionare il file e quindi selezionare **Apri**.
    - Per creare un saluto, selezionare **digitare un messaggio di saluto**e quindi digitare il messaggio. I chiamanti sentiranno questo messaggio se non hai fornito un file audio.
7. Per terminare la chiamata dopo il messaggio di saluto, in **azioni**selezionare **Disconnetti**. 

    Per reindirizzare la chiamata, selezionare **reindirizza chiamata**e quindi selezionare la persona che riceverà la chiamata reindirizzata dall'elenco a discesa o cercherà la persona per nome visualizzato.
8. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Che cosa sono gli operatori automatici di cloud](what-are-phone-system-auto-attendants.md)?
