---
title: Pianificare l'applicazione Annuncio in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Pianificazione dell'applicazione annuncio in Skype for Business Server VoIP aziendale, che configura cosa fare con le chiamate telefoniche a numeri di telefono non assegnati nelle organizzazioni. Include i requisiti per i file audio.
ms.openlocfilehash: 26dbd9a0bf1513812cb08034216194ca67a92b39
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778096"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Pianificare l'applicazione Annuncio in Skype for Business

Pianificazione dell'applicazione annuncio in Skype for Business Server VoIP aziendale, che configura cosa fare con le chiamate telefoniche a numeri di telefono non assegnati nelle organizzazioni. Include i requisiti per i file audio.

L'applicazione annuncio Skype for Business Server consente di configurare la gestione delle chiamate telefoniche in arrivo quando il numero composto è valido per l'organizzazione, ma non è assegnato a un utente o a un telefono. È possibile trasferire queste chiamate a una destinazione predeterminata (numero di telefono, URI SIP o segreteria telefonica) oppure riprodurre un annuncio audio o entrambe le opzioni. L'applicazione Annuncio consente di evitare il caso in cui un chiamante compone un numero errato e riceve un tono di occupato oppure il client SIP riceve un messaggio di errore. In questa sezione sono incluse informazioni sulla pianificazione specifiche per l'applicazione Annuncio

Quando si distribuisce l'applicazione Annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato. La tabella dei numeri non assegnati contiene intervalli di numeri di telefono validi per l'organizzazione e specifica quale applicazione annuncio gestisce ogni intervallo. Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non assegnato a nessuno, Skype for Business Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui rientra il numero e instrada la chiamata all'applicazione Annuncio specificata per tale intervallo. L'applicazione Annuncio risponde alla chiamata e riproduce un messaggio audio (se è stato configurato per farlo) e quindi disconnette la chiamata o la trasferisce a una destinazione predeterminata, ad esempio a un operatore. È possibile utilizzare Skype for Business Server Management Shell per configurare più messaggi audio o per trasferire destinazioni.

Il modo in cui configurare la tabella dei numeri non assegnati dipende da come si desidera usarla. Se si dispone di numeri specifici non più in uso e si desidera riprodurre messaggi personalizzati per ogni numero, è possibile immettere tali numeri specifici nella tabella dei numeri non assegnati. Se, ad esempio, è stato modificato il numero del Service Desk clienti, è possibile immettere il vecchio numero del servizio clienti e associarlo a un annuncio che fornisce il nuovo numero. Se si desidera riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per dipendenti che non lavorano più nell'organizzazione, è possibile immettere intervalli per tutti gli interni validi dell'organizzazione. La tabella dei numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero attualmente non assegnato.

## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Annuncio viene installata automaticamente con l'applicazione Response Group. Le applicazioni Annuncio e Response Group sono componenti standard di una distribuzione VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.

### <a name="software-requirements"></a>Requisiti software

In tutti i Front End Server o nei server edizione Standard che eseguono l'applicazione Annuncio deve essere installato Runtime formato multimediale di Windows per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte di Windows Desktop Experience. Windows Runtime formato multimediale o Microsoft Media Foundation è necessario per i Windows Media Audio (wma) riprodotti dall'applicazione Annuncio per annunci e musica.

### <a name="port-requirements"></a>Requisiti delle porte

L'applicazione Annuncio utilizza **la porta 5071** per le richieste di attesa SIP.

> [!NOTE]
> Questa porta è l'impostazione predefinita, che è possibile modificare utilizzando il cmdlet **Set-CsApplicationServer.** Per informazioni dettagliate su questo cmdlet, vedere la documentazione Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Annuncio supporta il formato di file Wave (wav) e Windows file audio multimediale (wma) per la musica e gli annunci. I requisiti dei file audio per l'applicazione Annuncio sono gli stessi dell'applicazione Response Group. Per informazioni dettagliate, vedere [Technical Requirements for Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).