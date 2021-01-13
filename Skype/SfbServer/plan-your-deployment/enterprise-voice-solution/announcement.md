---
title: Pianificare l'applicazione annuncio in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Pianificazione dell'applicazione annuncio in Skype for Business Server VoIP aziendale, in cui vengono configurate le operazioni da eseguire con le chiamate telefoniche ai numeri di telefono non assegnati nelle organizzazioni. Include i requisiti dei file audio.
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813756"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Pianificare l'applicazione annuncio in Skype for business

Pianificazione dell'applicazione annuncio in Skype for Business Server VoIP aziendale, in cui vengono configurate le operazioni da eseguire con le chiamate telefoniche ai numeri di telefono non assegnati nelle organizzazioni. Include i requisiti dei file audio.

L'applicazione Annuncio di Skype for Business Server consente di configurare la gestione delle chiamate in arrivo quando il numero composto è valido per l'organizzazione, ma non è assegnato a un utente o a un telefono. È possibile trasferire queste chiamate a una destinazione predeterminata (numero di telefono, URI SIP o segreteria telefonica) oppure riprodurre un annuncio audio o entrambe le opzioni. L'applicazione Annuncio consente di evitare il caso in cui un chiamante compone un numero errato e riceve un tono di occupato oppure il client SIP riceve un messaggio di errore. In questa sezione sono incluse informazioni sulla pianificazione specifiche dell'applicazione annuncio.

Quando si distribuisce l'applicazione annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato. La tabella numeri non assegnati contiene gli intervalli di numeri di telefono validi per l'organizzazione e specifica quale applicazione di annuncio gestisce ogni intervallo. Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non è assegnato a nessuno, Skype for Business Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui si trova il numero e instrada la chiamata all'applicazione annuncio specificata per tale intervallo. L'applicazione Annuncio risponde alla chiamata e riproduce un messaggio audio (se è stata configurata per farlo) e quindi disconnette la chiamata o la trasferisce in una destinazione predeterminata, ad esempio a un operatore. È possibile utilizzare i cmdlet di Skype for Business Server Management Shell per configurare più messaggi audio o per trasferire le destinazioni.

Il modo in cui configurare la tabella dei numeri non assegnati dipende da come si desidera usarla. Se si dispone di numeri specifici non più in uso e si desidera riprodurre messaggi personalizzati per ogni numero, è possibile immettere tali numeri specifici nella tabella dei numeri non assegnati. Se, ad esempio, è stato modificato il numero del Service Desk clienti, è possibile immettere il vecchio numero del servizio clienti e associarlo a un annuncio che fornisce il nuovo numero. Se si desidera riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per dipendenti che non lavorano più nell'organizzazione, è possibile immettere intervalli per tutti gli interni validi dell'organizzazione. La tabella dei numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero attualmente non assegnato.

## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Annuncio di Tthe viene automaticamente installata con l'applicazione Response Group. Le applicazioni annuncio e Response Group sono componenti standard di una distribuzione di VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.

### <a name="software-requirements"></a>Requisiti software

Tutti i Front End Server o i server Standard Edition che eseguono l'applicazione annuncio devono disporre del runtime del formato Windows Media per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, il runtime del formato Windows Media viene installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file Windows Media Audio (con estensione WMA) che l'applicazione annuncio riproduce per gli annunci e la musica.

### <a name="port-requirements"></a>Requisiti delle porte

L'applicazione annuncio utilizza la **porta 5071** per le richieste di attesa SIP.

> [!NOTE]
> Questa porta è l'impostazione predefinita, che può essere modificata utilizzando il cmdlet **Set-CsApplicationServer** . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Annuncio supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per la musica e gli annunci. I requisiti dei file audio per l'applicazione annuncio sono identici a quelli dell'applicazione Response Group. Per informazioni dettagliate, vedere [requisiti tecnici per i Response Group](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


