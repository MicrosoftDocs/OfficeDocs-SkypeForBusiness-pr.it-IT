---
title: Impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Informazioni sulle aree di rete, i siti di rete e le subnet IP. Tutti questi elementi devono essere configurati per distribuire il piano per il bypass multimediale in Skype for business, pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server o pianificare i servizi di emergenza in Skype for Business Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802596"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server

Informazioni sulle aree di rete, i siti di rete e le subnet IP. Tutti questi elementi devono essere configurati per distribuire il [piano per il bypass multimediale in Skype for business](media-bypass.md), [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](call-admission-control.md)o [pianificare i servizi di emergenza in Skype for business](emergency-services.md) server in Skype for Business Server VoIP aziendale.

Skype for Business Server offre tre funzionalità avanzate per la voce aziendale: [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](call-admission-control.md), [pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)e [pianificare il bypass multimediale in Skype for business](media-bypass.md). Queste caratteristiche condividono determinati requisiti di configurazione per le aree di rete, i siti di rete e l'associazione di ogni subnet nella topologia di Skype for Business Server con un sito di rete.

Questo argomento offre una panoramica dei requisiti di configurazione comuni a tutte e tre le funzionalità vocali avanzate di Enterprise.

## <a name="network-regions"></a>Aree di rete

Un'area di rete è un hub di rete o backbone di rete usato solo nella configurazione del controllo di ammissione alle chiamate (CAC), E9-1-1 e bypass multimediale.

> [!NOTE]
> Le aree di rete non corrispondono a quelle di Skype for Business Server per i servizi di conferenza telefonica con accesso esterno, necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più dial plan di Skype for Business Server. Per informazioni dettagliate sulle aree dei servizi di conferenza telefonica con accesso esterno, vedere [pianificazione per i servizi di conferenza telefonica con accesso esterno](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

Il CAC richiede che ogni area di rete disponga di un sito centrale Skype for Business Server associato, che gestisce il traffico multimediale all'interno dell'area geografica, ovvero prende decisioni in base a criteri configurati, per quanto riguarda la possibilità di un audio in tempo reale o la sessione video può essere stabilita). I siti centrali di Skype for Business Server non rappresentano posizioni geografiche, bensì gruppi logici di server configurati come pool o set di pool.

Per configurare un'area di rete, è possibile usare la scheda **aree** nella sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure eseguire i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** di Skype for Business Server Management Shell. Per istruzioni, vedere [distribuire aree di rete, siti e subnet in Skype for business](../../deploy/deploy-enterprise-voice/deploy-network.md) nella documentazione di distribuzione oppure fare riferimento alla documentazione relativa a Skype for Business Server Management Shell.

Le stesse definizioni di area di rete sono condivise da tutte e tre le funzionalità vocali avanzate di Enterprise. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per le altre funzionalità. Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche. Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e, in seguito, si distribuisce il controllo di ammissione di chiamata, è necessario modificare ogni definizione di area di rete per specificare un sito centrale.

Per associare un sito centrale di Skype for Business Server a un'area di rete, devi specificare il nome del sito centrale usando la sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure eseguendo i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** . Per istruzioni, vedere [distribuire aree di rete, siti e subnet in Skype for business](../../deploy/deploy-enterprise-voice/deploy-network.md) nella documentazione di distribuzione oppure fare riferimento alla documentazione relativa a Skype for Business Server Management Shell.

## <a name="network-sites"></a>Siti di rete

Un sito di rete rappresenta una posizione geografica, ad esempio una filiale, un ufficio regionale o una sede principale. Ogni sito di rete deve essere associato a una specifica area di rete.

> [!NOTE]
> I siti di rete vengono usati solo dalle funzionalità vocali avanzate di Enterprise. Non sono uguali ai siti della filiale configurati nella topologia di Skype for Business Server.

Per configurare un sito di rete e associarlo a un'area di rete, è possibile usare la sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure eseguire i cmdlet **New-CsNetworkSite** o **Set-CsNetworkSite** di Skype for Business Server Management Shell. Per informazioni dettagliate, vedere [creare o modificare un sito di rete](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) nella documentazione di distribuzione oppure fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete, è necessario collaborare con l'amministratore di rete per determinare le subnet IP assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP nelle aree di rete e nei siti di rete, il lavoro è semplificato in modo significativo.

Ad esempio, il sito di New York nell'area Nord America può essere assegnato alle subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, che lavora di solito a Detroit, viaggia all'ufficio di New York per la formazione, accende il computer e si connette alla rete, il computer otterrà un indirizzo IP in uno dei quattro intervalli assegnati a New York, ad esempio 172.29.80.103.

> [!CAUTION]
> Le subnet IP specificate durante la configurazione di rete nel server devono corrispondere al formato fornito dai computer client per essere correttamente usati per il bypass multimediale. Un client Skype for business prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Quando si determina l'ID di bypass associato a ogni client, il registrar confronterà l'elenco delle subnet IP associate a ogni sito di rete rispetto alla subnet fornita dal client per una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione di rete sul server siano subnet effettive anziché sottoreti virtuali. Se si distribuisce il controllo di ammissione alle chiamate, ma non il bypass multimediale, il controllo di ammissione delle chiamate funzionerà correttamente anche se si configurano sottoreti virtuali. Ad esempio, se un client Skype for business accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, richiederà l'ID di bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, il registrar non considererà questa corrispondenza perché il registrar Cerca specificamente la subnet 172.29.81.0. Di conseguenza, è importante che l'amministratore immetta le subnet esattamente come previsto dai client Skype for business (che vengono provisionati con le subnet durante la configurazione della rete, sia in modo statico che tramite DHCP).

## <a name="associating-subnets-with-network-sites"></a>Associazione di subnet con i siti di rete

Ogni subnet nella rete aziendale deve essere associata a un sito di rete, ovvero ogni subnet deve essere associata a una posizione geografica. Questa associazione di subnet consente alle funzionalità vocali avanzate dell'organizzazione di individuare gli endpoint geograficamente. Ad esempio, l'individuazione degli endpoint consente a CAC di regolare il flusso di dati audio e video in tempo reale da e verso il sito di rete.

Per associare subnet a siti di rete, è possibile usare la sezione **configurazione di rete** del pannello di controllo di Skype for Business Server oppure usare Skype for Business Server Management Shell. Per istruzioni, vedere [associare una subnet a un sito di rete](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) nella documentazione di distribuzione oppure fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="see-also"></a>Vedere anche

[Pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](call-admission-control.md)

[Pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)

[Pianificare il bypass multimediale in Skype for business](media-bypass.md)

