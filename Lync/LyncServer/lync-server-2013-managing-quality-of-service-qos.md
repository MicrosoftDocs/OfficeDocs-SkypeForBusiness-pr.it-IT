---
title: 'Lync Server 2013: gestione della qualità del servizio (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72fbd1275060ce01d56cb64e11cdd27f38b2e54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Gestione della qualità del servizio (QoS) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

Quality of Service (QoS) è una tecnologia di rete utilizzata in alcune organizzazioni per fornire un'esperienza utente ottimale per le comunicazioni audio e video. La funzionalità QoS è più comunemente utilizzata nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete in competizione per una quantità relativamente ridotta di larghezza di banda disponibile, la qualità del servizio consente agli amministratori di assegnare priorità più elevate ai pacchetti trasporto di dati audio o video. Assegnando a questi pacchetti una priorità più elevata, è probabile che le comunicazioni audio e video vengano completate più velocemente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come il trasferimento di file, la navigazione web o i backup dei database. Ciò è dovuto al fatto che i pacchetti di rete utilizzati per i trasferimenti di file o i backup dei database sono assegnati come priorità "Best Effort".

<div>


> [!NOTE]  
> Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione sulla rete interna. Quando si implementa QoS, i server e i router vengono configurati in modo da supportare la marcatura dei pacchetti. Tuttavia, è necessario configurare questi dispositivi per supportare il contrassegno dei pacchetti in un modo specifico. Non è possibile presumere che la qualità del servizio sarà supportata su Internet o su altre reti. Anche se la qualità se il servizio è supportato su altre reti, non vi è alcuna garanzia che QoS venga configurato nello stesso modo in cui è stato configurato il servizio sulla rete.



</div>

Microsoft Lync Server 2013 non richiede la qualità del servizio. Se attualmente non si utilizza QoS, non è necessario installare il servizio prima di installare Lync Server 2013. Se si verifica una notevole quantità di perdita di pacchetti sulla rete, il modo consigliato per alleviare questo problema consiste nell'aggiungere ulteriore larghezza di banda. Se non è possibile aggiungere più larghezza di banda, potrebbe essere necessario implementare invece la qualità del servizio.

Lync Server 2013 offre supporto completo per la qualità del servizio: ciò significa che le organizzazioni che utilizzano già QoS possono integrare facilmente Lync Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire le attività seguenti:

  - [Abilitazione del QoS in Lync Server 2013 per dispositivi che non sono basati su Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitata per i computer e altri dispositivi (ad esempio iPhones) che eseguono altri sistemi operativi. Anche se è possibile utilizzare Lync Server per abilitare e disabilitare la qualità del servizio per i dispositivi, non è in genere possibile utilizzare il prodotto per modificare i codici DSCP utilizzati da questi dispositivi.

  - [Configurazione degli intervalli di porte in Lync server 2013 per i servizi di conferenza, applicazione e Mediation Server](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario riservare un insieme univoco di porte per diversi tipi di pacchetti, ad esempio audio e video. Con Lync Server 2013 non è possibile abilitare o disabilitare la qualità del servizio, ad esempio, l'impostazione di un valore della proprietà su true o su false. In alternativa, è possibile abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo. Se in seguito si decide di non utilizzare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo corretti.

  - [Configurazione degli intervalli di porte per i server perimetrali in Lync server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Sebbene non sia necessario, è possibile configurare i server perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server.

  - [Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Questi intervalli di porte si applicano solo ai computer client e in genere non corrispondono agli intervalli di porte configurati nei server.

  - [Configurazione dei criteri di qualità del servizio in Lync server 2013 per i servizi di conferenza, applicazione e Mediation Server](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Questi criteri determinano i codici DSCP applicati ai diversi tipi di pacchetti.

  - [Configurazione dei criteri di qualità del servizio per i server a/V Edge in Lync server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Tale operazione deve essere completata solo per il lato interno dei server perimetrali. Ciò è dovuto al fatto che la qualità del servizio è progettata per essere utilizzata sulla rete interna e non su Internet.

  - [Configurazione dei criteri di qualità del servizio in Lync Server 2013 per i client in esecuzione in Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Si noti che Microsoft Lync Server 2013 non supporta QoS per altri sistemi operativi Windows, ad esempio Windows Vista o Windows XP.

  - [Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Per impostazione predefinita, QoS è abilitata per i dispositivi Lync Phone Edition. Tuttavia, potrebbe essere necessario modificare il valore DSCP predefinito per assicurarsi che tutti i pacchetti audio nell'organizzazione utilizzino lo stesso codice DSCP.

<div>


> [!NOTE]  
> Se si utilizza Microsoft Windows Server 2012 o Windows Server 2012 R2, potrebbe essere interessato al nuovo set di cmdlet di Windows PowerShell disponibili per la gestione della qualità del servizio su tale piattaforma. Per ulteriori informazioni, vedere cmdlet per la qualità dei servizi di rete in Windows [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)PowerShell all'indirizzo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

