---
title: Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Skype for Business Server
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
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Informazioni sulle aree di rete, sui siti di rete e sulle subnet IP. Tutti questi elementi devono essere configurati per la distribuzione del piano per il bypass multimediale in Skype for business, pianificare il controllo di ammissione di chiamata in Skype for Business Server o pianificare i servizi di emergenza in Skype for Business Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3f7b11d2265c9b5f93633b03311d622ad9862abd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813626"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Skype for Business Server

Informazioni sulle aree di rete, sui siti di rete e sulle subnet IP. Tutti questi elementi devono essere configurati per la distribuzione del [piano per il bypass multimediale in Skype for business](media-bypass.md), [pianificare il controllo di ammissione di chiamata in Skype for Business Server](call-admission-control.md)o [pianificare i servizi di emergenza in Skype for business](emergency-services.md) server in Skype for Business Server VoIP aziendale.

Skype for Business Server ha tre funzionalità di VoIP aziendale avanzate: [pianificare il controllo di ammissione di chiamata in Skype for Business Server](call-admission-control.md), [pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)e [pianificare il bypass multimediale in Skype for business](media-bypass.md). Tali caratteristiche condividono alcuni requisiti di configurazione per le aree di rete, i siti di rete e l'associazione di ogni subnet nella topologia di Skype for Business Server con un sito di rete.

In questo argomento viene fornita una panoramica dei requisiti di configurazione comuni a tutte e tre queste funzionalità avanzate di VoIP aziendale.

## <a name="network-regions"></a>Aree di rete

Un'area di rete è un hub o un backbone di rete utilizzato solo nella configurazione dei servizi Controllo di ammissione di chiamata, E9-1-1 e Media Bypass.

> [!NOTE]
> Le aree di rete non corrispondono alle aree di conferenza telefonica con accesso esterno di Skype for Business Server, che sono necessarie per associare i numeri di telefono per le conferenze telefoniche con chiamata in ingresso con uno o più dial plan di Skype for Business Server. Per informazioni dettagliate sulle aree di conferenza telefonica con accesso esterno, vedere [pianificazione delle conferenze](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)telefoniche con accesso esterno.

Il servizio CAC richiede che ogni area di rete disponga di un sito centrale di Skype for Business Server associato, che gestisce il traffico multimediale all'interno dell'area (ovvero prende decisioni basate sui criteri configurati, per quanto riguarda la possibilità di stabilire o meno una sessione audio o video in tempo reale). I siti centrali di Skype for Business Server non rappresentano posizioni geografiche, ma piuttosto gruppi logici di server configurati come pool o come set di pool.

Per configurare un'area di rete, è possibile utilizzare la scheda **aree** della sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure eseguire i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** per Skype for Business Server Management Shell. Per istruzioni, vedere [deploy Network Regions, sites and Subnets in Skype for business](../../deploy/deploy-enterprise-voice/deploy-network.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione su Skype for Business Server Management Shell.

Le stesse definizioni di aree di rete sono condivise da tutte e tre le funzionalità di VoIP aziendale avanzate. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per le altre caratteristiche. Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica. Se, ad esempio, sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e successivamente si distribuisce il servizio Controllo di ammissione di chiamata, è necessario modificare ognuna delle definizioni di area di rete per specificare un sito centrale.

Per associare un sito centrale di Skype for Business Server a un'area di rete, è necessario specificare il nome del sito centrale utilizzando la sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure eseguendo i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** . Per istruzioni, vedere [deploy Network Regions, sites and Subnets in Skype for business](../../deploy/deploy-enterprise-voice/deploy-network.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione su Skype for Business Server Management Shell.

## <a name="network-sites"></a>Siti di rete

Un sito di rete rappresenta una posizione geografica, ad esempio una succursale, una filiale o la sede principale. Ogni sito di rete deve essere associato a un'area di rete specifica.

> [!NOTE]
> I siti di rete vengono utilizzati solo dalle funzionalità avanzate di VoIP aziendale. Non sono gli stessi dei siti di succursale configurati nella topologia di Skype for Business Server.

Per configurare un sito di rete e associarlo a un'area di rete, è possibile utilizzare la sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure eseguire il cmdlet **New-CsNetworkSite** o **Set-CsNetworkSite** di Skype for Business Server Management Shell. Per ulteriori informazioni, vedere [creare o modificare un sito di rete](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete sarà necessario collaborare con l'amministratore di rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.

In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli allocati a New York, ad esempio 172.29.80.103.

> [!CAUTION]
> Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per Media Bypass. Un client Skype for business prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Durante la determinazione dell'ID bypass associato a ogni client, tramite la funzione di registrazione viene confrontato l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali. Se si distribuisce il controllo di ammissione di chiamata, ma non il bypass multimediale, il controllo di ammissione di chiamata funzionerà correttamente anche se si configurano le subnet virtuali. Ad esempio, se un client Skype for business accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP di 255.255.255.0, richiederà l'ID di bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0. Pertanto, è importante che l'amministratore entri nelle subnet esattamente come indicato dai client Skype for business (che vengono provisionati con le subnet durante la configurazione di rete, sia in modo statico che tramite il protocollo DHCP (Dynamic Host Configuration Protocol).

## <a name="associating-subnets-with-network-sites"></a>Associazione di subnet a siti di rete

Ogni subnet della rete aziendale deve essere associata a un sito di rete (ovvero ogni subnet deve essere associata a una posizione geografica). Questa associazione di subnet consente alle funzionalità di VoIP aziendale avanzate di individuare i punti finali in modo geografico. L'individuazione degli endpoint consente, ad esempio, al servizio Controllo di ammissione di chiamata di regolare il flusso di dati audio e video in tempo reale da e verso il sito di rete.

Per associare subnet a siti di rete, è possibile utilizzare la sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure è possibile utilizzare Skype for Business Server Management Shell. Per istruzioni, vedere [associare una subnet a un sito di rete](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="see-also"></a>Vedere anche

[Pianificare il controllo di ammissione di chiamata in Skype for Business Server](call-admission-control.md)

[Pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)

[Pianificare il bypass multimediale in Skype for business](media-bypass.md)

