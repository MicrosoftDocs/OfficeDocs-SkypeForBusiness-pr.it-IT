---
title: Pianificare l'applicazione di annunci in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Pianificazione dell'applicazione di annunci in Skype for Business Server VoIP aziendale, che configura le operazioni da eseguire con le chiamate telefoniche a numeri di telefono non assegnati nelle organizzazioni. Include i requisiti per i file audio.
ms.openlocfilehash: af7ce9fdcfa78daa875a4748eafac5020246b74b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187802"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Pianificare l'applicazione di annunci in Skype for business

Pianificazione dell'applicazione di annunci in Skype for Business Server VoIP aziendale, che configura le operazioni da eseguire con le chiamate telefoniche a numeri di telefono non assegnati nelle organizzazioni. Include i requisiti per i file audio.

L'applicazione di annuncio di Skype for Business Server consente di configurare la gestione delle chiamate in arrivo quando il numero di telefono è valido per l'organizzazione, ma non viene assegnato a un utente o a un telefono. È possibile trasferire queste chiamate a una destinazione predeterminata (numero di telefono, URI SIP o segreteria telefonica) oppure riprodurre un annuncio audio o entrambi. L'applicazione di annuncio consente di evitare le situazioni in cui un chiamante effettua una chiamata errata e sente un tono di occupato o il client SIP riceve un messaggio di errore. Questa sezione include informazioni sulla pianificazione specifiche dell'applicazione di annuncio

Quando si distribuisce l'applicazione di annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato. La tabella numero non assegnati contiene gli intervalli di numeri di telefono validi per l'organizzazione e specifica l'applicazione di un annuncio che gestisce ogni intervallo. Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non è assegnato a nessuno, Skype for Business Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui il numero rientra e instrada la chiamata al Applicazione di annuncio specificata per tale intervallo. L'applicazione di annuncio risponde alla chiamata e riproduce un messaggio audio (se è stato configurato per farlo) e quindi disconnette la chiamata o la trasferisce a una destinazione predeterminata, ad esempio a un operatore. Puoi usare i cmdlet di Skype for Business Server Management Shell per configurare più messaggi audio o per trasferire destinazioni.

La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. Se si hanno numeri specifici che non sono più in uso e si vogliono riprodurre i messaggi personalizzati per ogni numero, è possibile immettere i numeri specifici nella tabella dei numeri non assegnati. Se ad esempio è stato modificato il numero per il servizio di assistenza clienti, è possibile immettere il vecchio numero di servizio clienti e associarlo a un annuncio che fornisce il nuovo numero. Se si vuole riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per i dipendenti che hanno lasciato l'organizzazione, è possibile immettere gli intervalli per tutte le estensioni valide dell'organizzazione. La tabella numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero che non è attualmente assegnato.

## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione di annunci il viene installata automaticamente con l'applicazione Response Group. Le applicazioni per l'annuncio e il gruppo di risposta sono componenti standard di una distribuzione di VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.

### <a name="software-requirements"></a>Requisiti software

Tutti i server front-end o i server Standard Edition che eseguono l'applicazione annunci devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che l'applicazione di annuncio riproduce per gli annunci e la musica.

### <a name="port-requirements"></a>Requisiti della porta

L'applicazione di annuncio usa la **porta 5071** per le richieste di ascolto SIP.

> [!NOTE]
> Questa porta è l'impostazione predefinita, che può essere modificata usando il cmdlet **Set-CsApplicationServer** . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Requisiti per i file audio

L'applicazione di annuncio supporta il formato di file Wave (con estensione wav) e il formato di file WMA (Windows Media Audio) per musica e annunci. I requisiti per i file audio per l'applicazione di annuncio sono gli stessi per l'applicazione Response Group. Per informazioni dettagliate, vedere [requisiti tecnici per i gruppi di risposta](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).


