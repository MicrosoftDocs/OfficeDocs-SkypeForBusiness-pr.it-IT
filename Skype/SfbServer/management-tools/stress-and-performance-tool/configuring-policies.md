---
title: Configurazione dei criteri per lo strumento Skype for Business Server 2015 Stress and Performance
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
description: Configurazione dei criteri per Skype for Business Server 2015 Stress and Performance Tool.
ms.openlocfilehash: 0a7e93e0e6a25195b1e9723ce6eb31b4c9f9fbd200d390f225a2be29c4106b0a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333188"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configurazione dei criteri per lo strumento Skype for Business Server 2015 Stress and Performance
 
Configurazione dei criteri per Skype for Business Server 2015 Stress and Performance Tool.
  
Esistono diversi criteri e altre aree che è possibile configurare in Skype for Business Server 2015, prima di eseguire lo strumento Stress and Performance:
  
- [Criteri di archiviazione](configuring-policies.md#ArchivingPolicy)
    
- [Criteri conferenza](configuring-policies.md#ConferencingPolicy)
    
- [Criteri contatti](configuring-policies.md#ContactsPolicy)
    
- [Criteri di federazione](configuring-policies.md#FederationPolicy)
    
- [Criteri controllo di ammissione di chiamata](configuring-policies.md#CACPolicy)
    
- [Regole di routing vocale](configuring-policies.md#VoiceRoutingRules)
    
- [Applicazione Operatore conferenza](configuring-policies.md#ConfAttendantApp)
    
- [Servizio Parcheggio di chiamata del server](configuring-policies.md#ServerCallParkServ)
    
- [Chiamate di emergenza](configuring-policies.md#EmergencyCalls)
    
- [Configurazione dell'applicazione Response Group](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Criteri di archiviazione
<a name="ArchivingPolicy"> </a>

Se si dispone di un server di archiviazione distribuito nella topologia Skype for Business Server, è possibile esaminare lo script ArchivingPolicy.ps1. Per ulteriore assistenza, consultare i cmdlet di archiviazione e Web Conferencing.
  
## <a name="conferencing-policy"></a>Criteri conferenza
<a name="ConferencingPolicy"> </a>

Per le conferenze, è stato creato lo script MeetingPolicy.ps1 conferenza. Se è necessaria ulteriore assistenza, consultare i cmdlet web conferencing.
  
## <a name="contacts-policy"></a>Criteri contatti
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 script sarà l'esempio da esaminare. I cmdlet di messaggistica istantanea e presenza sono utili se sono necessari ulteriori riferimenti.
  
## <a name="federation-policy"></a>Criteri di federazione
<a name="FederationPolicy"> </a>

Lo script di esempio per la federazione è FederationPolicy.ps1. I cmdlet da esaminare, se sono necessarie ulteriori informazioni, saranno Server perimetrale, federazione e accesso esterno.
  
## <a name="call-admission-control-policy"></a>Criteri controllo di ammissione di chiamata
<a name="CACPolicy"> </a>

È possibile fare riferimento BandwidthPolicy.ps1 per questo criterio. I cmdlet di Controllo di ammissione di chiamata diverranno inoltre disponibili ulteriori informazioni.
  
## <a name="voice-routing-rules"></a>Regole di routing vocale
<a name="VoiceRoutingRules"> </a>

You'll need the RoutingRules.ps1 sample script for Voice Routing. Quando configuri queste regole, prendi nota del contesto del telefono (ovvero /Location Profile o /SimpleName) e dei codici di area interna/esterna, in modo da poterle specificare durante la creazione degli utenti. Saranno necessari anche durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).
  
Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules.ps1 deve essere utilizzato per il valore LocationProfile nella figura seguente di UserProfileGenerator.exe:
  
![Skype for Business strumento di configurazione del carico, scheda Scenari vocali, Impostazioni avanzate per conversazioni.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Per informazioni dettagliate, è possibile esaminare VoIP aziendale cmdlet.
  
## <a name="conference-attendant-application"></a>Applicazione Operatore conferenza
<a name="ConfAttendantApp"> </a>

Esaminare innanzitutto lo script ConferenceAutoAttendantConfiguration.ps1. È necessario prendere nota del numero di telefono ConferencingAutoAttendant (1121111111 per impostazione predefinita), in modo da poterlo immettere nello strumento di configurazione LyncPerfTool per la generazione della configurazione, come indicato di seguito:
  
![Scheda Scenari vocali che mostra il livello di carico di conferenza e il numero di telefono.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Per ulteriori dettagli, vedere Conferencing and Dial-in Conferencing cmdlets.
  
## <a name="server-call-park-service"></a>Servizio Parcheggio di chiamata del server
<a name="ServerCallParkServ"> </a>

Questa opzione è effettivamente disabilitata per impostazione predefinita. È possibile esaminare lo script CallParkConfiguration.ps1 esempio se è necessario testare questo script. Inoltre, consultare i cmdlet dell'applicazione parcheggio di chiamata in base alle esigenze.
  
## <a name="emergency-calls"></a>Chiamate di emergenza
<a name="EmergencyCalls"> </a>

Per configurare i test di stress e prestazioni per le chiamate di emergenza, è necessario eseguire la procedura seguente:
  
1. Configurare una route vocale per le chiamate di emergenza. È possibile utilizzare lo script RoutingRules.ps1 e controllare sotto il commento " **Route E911 to PSTN** " per un esempio di come configurare questa route vocale.
    
    > [!CAUTION]
    > Il comando di esempio in RoutingRules.ps1 ha un formato di numero che include il numero 119 anziché 911. È consigliabile evitare di usare il 911 (o il numero di emergenza locale effettivo) per evitare chiamate accidentali agli operatori di emergenza locali durante i test di carico. Tenere presente che questa configurazione è solo a scopo di simulazione. 
  
2. Configurare gli indirizzi compilando i valori nella scheda **Configurazione** servizio informazioni percorso in UserProvisioningTool, come illustrato nella figura seguente:
    
     ![Strumento di provisioning degli utenti che mostra il numero di indirizzi, subnet, commutatori e porte.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Dopo aver immesso tutto nello UserProvisioningTool, fare clic sul **pulsante Genera file di configurazione LIS.**
    
4. Ora verranno generati file CSV per porte, subnet, commutatori e punti di accesso wireless (WAP), nonché un file XML per lo strumento Stress and Performance. È possibile utilizzare i file CSV per gli input quando si configura il servizio informazioni percorso (LIS) con lo script LisConfiguration.ps1 locale. A tale scopo, dovrai spostare il file Locations0.xml nella stessa cartella del file eseguibile dello strumento stress e prestazioni (LyncPerfTool.exe). In questo modo è possibile eseguire scenari di profilo località (dial plan).
    
## <a name="configuring-response-group-application"></a>Configurazione dell'applicazione Response Group
<a name="ConfigResponseGroupApp"> </a>

Lo script di esempio è ResponseGroupConfiguration.ps1. Sono inoltre disponibili cmdlet dell'applicazione Response Group da esaminare per ulteriori dettagli sulla configurazione. Nel diagramma seguente vengono mostrati alcuni dei dettagli di configurazione:
  
![Strumento di configurazione di Response Group che mostra i flussi di lavoro esistenti per i test.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

