---
title: Impostazioni di rete per le funzionalità VoIP aziendale avanzate in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Informazioni sulle aree di rete, i siti di rete e le subnet IP. Tutti questi elementi devono essere configurati per distribuire Plan for media bypass in Skype for Business, Plan for call admission control in Skype for Business Server) o Plan for emergency services in Skype for Business Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 97cf81bb3efa9aa5d4b8717018232d479fcbf2c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608003"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Impostazioni di rete per le funzionalità VoIP aziendale avanzate in Skype for Business Server

Informazioni sulle aree di rete, i siti di rete e le subnet IP. Tutti questi elementi devono essere configurati per distribuire Plan [for media bypass in Skype for Business,](media-bypass.md)Plan for call admission control in [Skype for Business Server](call-admission-control.md)o Plan for emergency services [in Skype for Business Server](emergency-services.md) in Skype for Business Server VoIP aziendale.

Skype for Business Server dispone di tre funzionalità VoIP aziendale avanzate: Pianificare il controllo di ammissione di chiamata [in Skype for Business Server,](call-admission-control.md)Pianificare i servizi di emergenza [in Skype for Business Server](emergency-services.md)e Pianificare il bypass multimediale [in Skype for Business](media-bypass.md). Queste funzionalità condividono determinati requisiti di configurazione per le aree di rete, i siti di rete e l'associazione di ogni subnet nella topologia Skype for Business Server con un sito di rete.

In questo argomento viene fornita una panoramica dei requisiti di configurazione comuni a tutte e tre queste funzionalità VoIP aziendale avanzate.

## <a name="network-regions"></a>Aree di rete

Un'area di rete è un hub o un backbone di rete utilizzato solo nella configurazione dei servizi Controllo di ammissione di chiamata, E9-1-1 e Media Bypass.

> [!NOTE]
> Le aree di rete non sono uguali Skype for Business Server aree di conferenza telefonica con accesso esterno, necessarie per associare i numeri di accesso alle conferenze telefoniche con accesso esterno a uno o più dial plan Skype for Business Server chiamata. Per informazioni dettagliate sulle aree di conferenza telefonica con accesso esterno, vedere [Planning for Dial-In Conferencing.](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements)

Il servizio controllo di ammissione di chiamata richiede che a ogni area di rete sia associato un sito centrale di Skype for Business Server, che gestisce il traffico multimediale all'interno dell'area, ovvero prende decisioni in base ai criteri configurati dall'utente, indipendentemente dal fatto che sia possibile stabilire o meno una sessione audio o video in tempo reale. Skype for Business Server siti centrali non rappresentano posizioni geografiche, ma gruppi logici di server configurati come pool o set di pool.

Per configurare un'area di rete, è  possibile utilizzare la scheda Aree nella sezione Configurazione di rete del Pannello di controllo di Skype for Business Server oppure eseguire i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** Skype for Business Server Management Shell.  Per istruzioni, vedere [Deploy network regions, sites and subnets in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Skype for Business Server Management Shell.

Le stesse definizioni di area di rete sono condivise da tutte e tre le funzionalità VoIP aziendale avanzate. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per le altre caratteristiche. Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica. Se, ad esempio, sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e successivamente si distribuisce il servizio Controllo di ammissione di chiamata, è necessario modificare ognuna delle definizioni di area di rete per specificare un sito centrale.

Per associare un sito centrale di Skype for Business Server a un'area di rete, specificare il nome del sito centrale utilizzando la sezione Configurazione di rete del Pannello di controllo di Skype for Business Server oppure eseguendo i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion.**  Per istruzioni, vedere [Deploy network regions, sites and subnets in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="network-sites"></a>Siti di rete

Un sito di rete rappresenta una posizione geografica, ad esempio una succursale, una filiale o la sede principale. Ogni sito di rete deve essere associato a un'area di rete specifica.

> [!NOTE]
> I siti di rete vengono utilizzati solo dalle funzionalità VoIP aziendale avanzate. Non sono uguali ai siti di succursale che si configurano nella topologia Skype for Business Server locale.

Per configurare un sito di rete e associarlo a  un'area di rete, è possibile utilizzare la sezione Configurazione di rete del Pannello di controllo di Skype for Business Server oppure eseguire i cmdlet Skype for Business Server Management Shell **New-CsNetworkSite** o **Set-CsNetworkSite.** Per informazioni dettagliate, vedere [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) nella documentazione relativa alla distribuzione oppure fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete sarà necessario collaborare con l'amministratore di rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.

In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli allocati a New York, ad esempio 172.29.80.103.

> [!CAUTION]
> Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per Media Bypass. Un Skype for Business client accetta l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Durante la determinazione dell'ID bypass associato a ogni client, tramite la funzione di registrazione viene confrontato l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali. Se si distribuisce il controllo di ammissione di chiamata, ma non il bypass multimediale, il controllo di ammissione di chiamata funzionerà correttamente anche se si configurano subnet virtuali. Ad esempio, se un client Skype for Business accede a un computer con indirizzo IP 172.29.81.57 con una subnet mask IP di 255.255.255.0, richiederà l'ID bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0. Pertanto, è importante che l'amministratore immissione subnet esattamente come fornito dai client Skype for Business (di cui viene eseguito il provisioning con subnet durante la configurazione di rete, in modo statico o tramite DHCP (Dynamic Host Configuration Protocol).)

## <a name="associating-subnets-with-network-sites"></a>Associazione di subnet a siti di rete

Ogni subnet della rete aziendale deve essere associata a un sito di rete (ovvero ogni subnet deve essere associata a una posizione geografica). Questa associazione di subnet consente alle funzionalità VoIP aziendale avanzate di individuare gli endpoint geograficamente. L'individuazione degli endpoint consente, ad esempio, al servizio Controllo di ammissione di chiamata di regolare il flusso di dati audio e video in tempo reale da e verso il sito di rete.

Per associare subnet a siti di  rete, è possibile utilizzare la sezione Configurazione di rete del Pannello di controllo di Skype for Business Server oppure Skype for Business Server Management Shell. Per istruzioni, vedere [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Skype for Business Server Management Shell.

## <a name="see-also"></a>Vedere anche

[Pianificare il controllo di ammissione di chiamata in Skype for Business Server](call-admission-control.md)

[Pianificare i servizi di emergenza in Skype for Business Server](emergency-services.md)

[Pianificare il bypass multimediale in Skype for Business](media-bypass.md)