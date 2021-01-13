---
title: Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815036"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015
 
Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015.
  
Sono disponibili diversi criteri e altre aree che è possibile configurare in Skype for Business Server 2015, prima di eseguire lo strumento stress and performance:
  
- [Criteri di archiviazione](configuring-policies.md#ArchivingPolicy)
    
- [Criteri conferenza](configuring-policies.md#ConferencingPolicy)
    
- [Criteri contatti](configuring-policies.md#ContactsPolicy)
    
- [Criteri di Federazione](configuring-policies.md#FederationPolicy)
    
- [Criterio di controllo di ammissione di chiamata](configuring-policies.md#CACPolicy)
    
- [Regole di routing vocale](configuring-policies.md#VoiceRoutingRules)
    
- [Applicazione Operatore Conferenza](configuring-policies.md#ConfAttendantApp)
    
- [Servizio parcheggio di chiamata del server](configuring-policies.md#ServerCallParkServ)
    
- [Chiamate di emergenza](configuring-policies.md#EmergencyCalls)
    
- [Configurazione dell'applicazione Response Group](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Criteri di archiviazione
<a name="ArchivingPolicy"> </a>

Se si dispone di un server di archiviazione distribuito nella topologia di Skype for Business Server, è possibile esaminare lo script ArchivingPolicy.ps1. Se si necessita di ulteriore assistenza, vedere i cmdlet di archiviazione e Web Conferencing.
  
## <a name="conferencing-policy"></a>Criteri conferenza
<a name="ConferencingPolicy"> </a>

Per le conferenze, è presente lo script MeetingPolicy.ps1. Se si necessita di ulteriore assistenza, vedere i cmdlet per la Web Conferencing.
  
## <a name="contacts-policy"></a>Criteri contatti
<a name="ContactsPolicy"> </a>

Lo script ContactsPolicy.ps1 sarà l'esempio di cui è necessario eseguire la revisione. I cmdlet per la messaggistica istantanea e la presenza contribuiranno se sono necessari ulteriori riferimenti.
  
## <a name="federation-policy"></a>Criteri di Federazione
<a name="FederationPolicy"> </a>

Lo script di esempio per la Federazione è FederationPolicy.ps1. I cmdlet da esaminare, se si necessita di ulteriori informazioni, saranno server perimetrali, la Federazione e l'accesso esterno.
  
## <a name="call-admission-control-policy"></a>Criterio di controllo di ammissione di chiamata
<a name="CACPolicy"> </a>

È possibile fare riferimento a BandwidthPolicy.ps1 per questo criterio. I cmdlet per il controllo di ammissione di chiamata avranno anche altre informazioni.
  
## <a name="voice-routing-rules"></a>Regole di routing vocale
<a name="VoiceRoutingRules"> </a>

È necessario lo script di esempio RoutingRules.ps1 per il routing vocale. Quando si configurano queste regole, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni, in modo da poterli specificare quando si creano gli utenti. Sono inoltre necessari durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).
  
Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'RoutingRules.ps1 esempio deve essere utilizzato per il valore LocationProfile nella figura seguente di UserProfileGenerator.exe:
  
![Strumento di configurazione del caricamento di Skype for business, scheda scenari vocali, impostazioni avanzate per le conversazioni.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Per informazioni dettagliate, è possibile esaminare i cmdlet di VoIP aziendale.
  
## <a name="conference-attendant-application"></a>Applicazione Operatore Conferenza
<a name="ConfAttendantApp"> </a>

Prima di tutto, esaminare lo script ConferenceAutoAttendantConfiguration.ps1. Si vorrà prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111 per impostazione predefinita), in modo che sia possibile immetterlo nello strumento di configurazione di LyncPerfTool per la generazione di configurazione, come indicato di seguito:
  
![La scheda scenari vocali che mostra il livello di carico e il numero di telefono per le conferenze.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Sono disponibili ulteriori dettagli nei cmdlet per le conferenze telefoniche con accesso esterno e per le conferenze telefoniche.
  
## <a name="server-call-park-service"></a>Servizio parcheggio di chiamata del server
<a name="ServerCallParkServ"> </a>

Questo è effettivamente disabilitato per impostazione predefinita. È possibile esaminare lo script di esempio CallParkConfiguration.ps1 se è necessario testarlo. Consultare inoltre i cmdlet dell'applicazione Parcheggio di chiamata in base alle esigenze.
  
## <a name="emergency-calls"></a>Chiamate di emergenza
<a name="EmergencyCalls"> </a>

È necessario eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza:
  
1. Impostare una route vocale per le chiamate di emergenza. È possibile utilizzare lo script RoutingRules.ps1 e controllare il commento " **Route E911 to PSTN** " per un esempio di come impostare la route vocale.
    
    > [!CAUTION]
    > Il comando di esempio in RoutingRules.ps1 ha un modello di numero che include il numero 119 anziché 911. È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per impedire chiamate accidentali agli operatori di emergenza locali durante il test di carico. Tenere presente che questa configurazione è solo per scopi di simulazione. 
  
2. Configurare gli indirizzi compilando i valori nella scheda **configurazione del servizio informazioni percorso** in UserProvisioningTool, come illustrato nella figura seguente:
    
     ![Strumento di provisioning degli utenti che mostra il numero di indirizzi, subnet, commutatori e porte.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Dopo aver immesso tutto in UserProvisioningTool, fare clic sul pulsante **genera file di configurazione LIS** .
    
4. Sono ora generati file CSV per porte, subnet, commutatori e punti di accesso wireless (WAP), nonché un file XML per lo strumento stress and performance. È possibile utilizzare i file CSV per gli input quando si configura il servizio informazioni percorso (LIS) con lo script LisConfiguration.ps1. A tale scopo, è necessario spostare il file Locations0.xml nella stessa cartella in cui si esegue l'esecuzione dello strumento stress and performance (LyncPerfTool.exe). In questo modo è possibile eseguire gli scenari del profilo percorso (dial plan).
    
## <a name="configuring-response-group-application"></a>Configurazione dell'applicazione Response Group
<a name="ConfigResponseGroupApp"> </a>

Lo script di esempio è ResponseGroupConfiguration.ps1. Sono inoltre disponibili cmdlet per l'applicazione Response Group per la revisione dei dettagli di configurazione. Nel diagramma seguente vengono illustrati alcuni dettagli di configurazione:
  
![Strumento di configurazione di Response Group che mostra i flussi di lavoro esistenti per il testing.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

