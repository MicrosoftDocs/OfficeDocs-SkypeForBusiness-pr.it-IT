---
title: Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015.
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195085"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015
 
Configurazione dei criteri per lo strumento di stress e prestazioni di Skype for Business Server 2015.
  
Esistono diversi criteri e altre aree che è possibile configurare in Skype for Business Server 2015, prima di eseguire lo strumento di stress e prestazioni:
  
- [Criteri di archiviazione](configuring-policies.md#ArchivingPolicy)
    
- [Criteri di conferenza](configuring-policies.md#ConferencingPolicy)
    
- [Criteri contatti](configuring-policies.md#ContactsPolicy)
    
- [Criteri federativi](configuring-policies.md#FederationPolicy)
    
- [Criteri di controllo dell'ammissione alle chiamate](configuring-policies.md#CACPolicy)
    
- [Regole di routing vocale](configuring-policies.md#VoiceRoutingRules)
    
- [Applicazione Operatore Conferenza](configuring-policies.md#ConfAttendantApp)
    
- [Servizio parcheggio di chiamata del server](configuring-policies.md#ServerCallParkServ)
    
- [Chiamate di emergenza](configuring-policies.md#EmergencyCalls)
    
- [Configurazione dell'applicazione Response Group](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Criteri di archiviazione
<a name="ArchivingPolicy"> </a>

Se si dispone di un server di archiviazione distribuito nella topologia di Skype for Business Server, è possibile esaminare lo script ArchivingPolicy. ps1. Per ulteriori informazioni, vedere i cmdlet per l'archiviazione e la Web Conferencing.
  
## <a name="conferencing-policy"></a>Criteri di conferenza
<a name="ConferencingPolicy"> </a>

Per i servizi di conferenza abbiamo lo script MeetingPolicy. ps1. Se è necessaria ulteriore assistenza, vedere i cmdlet di Web Conferencing.
  
## <a name="contacts-policy"></a>Criteri contatti
<a name="ContactsPolicy"> </a>

Lo script ContactsPolicy. ps1 sarà l'esempio che è necessario rivedere. I cmdlet di messaggistica istantanea e presenza ti aiuteranno se hai bisogno di ulteriori riferimenti.
  
## <a name="federation-policy"></a>Criteri federativi
<a name="FederationPolicy"> </a>

Lo script di esempio per la Federazione è FederationPolicy. ps1. I cmdlet da rivedere, se sono necessarie ulteriori informazioni, saranno Edge Server, Federation e Access esterno.
  
## <a name="call-admission-control-policy"></a>Criteri di controllo dell'ammissione alle chiamate
<a name="CACPolicy"> </a>

Puoi fare riferimento a BandwidthPolicy. ps1 per questo criterio. I cmdlet per il controllo dell'ammissione alle chiamate avranno anche altre informazioni.
  
## <a name="voice-routing-rules"></a>Regole di routing vocale
<a name="VoiceRoutingRules"> </a>

È necessario lo script di esempio RoutingRules. ps1 per il routing vocale. Quando si configurano queste regole, prendere nota del contesto telefonico (ovvero/location profile o/SimpleName) e dei codici di area interni/esterni, in modo da poterli specificare quando si creano utenti. Sarà inoltre necessario durante la configurazione di LyncPerfTool (in particolare per PSTN-UC e UC-PSTN).
  
Ad esempio, il parametro SimpleName nella chiamata al cmdlet **New-CsDialPlan** nell'esempio RoutingRules. ps1 deve essere usato per il valore LocationProfile nella figura seguente di UserProfileGenerator. exe:
  
![Strumento di configurazione del carico di Skype for business, scheda scenari vocali, impostazioni avanzate per le conversazioni.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Per informazioni dettagliate, è possibile esaminare i cmdlet di VoIP aziendale.
  
## <a name="conference-attendant-application"></a>Applicazione Operatore Conferenza
<a name="ConfAttendantApp"> </a>

Esaminare prima di tutto lo script ConferenceAutoAttendantConfiguration. ps1. Si vorrà prendere nota del numero di telefono di ConferencingAutoAttendant (1121111111 per impostazione predefinita), in modo che sia possibile immetterlo nello strumento di configurazione di LyncPerfTool per la generazione di configurazione, come indicato di seguito:
  
![Scheda scenari vocali che mostra il livello di carico e il numero di telefono di conferenza.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Sono disponibili altri dettagli nei cmdlet per i servizi di conferenza telefonica con accesso esterno.
  
## <a name="server-call-park-service"></a>Servizio parcheggio di chiamata del server
<a name="ServerCallParkServ"> </a>

Questo è effettivamente disabilitato per impostazione predefinita. Se necessario, è possibile verificare lo script di esempio CallParkConfiguration. ps1. Controlla inoltre i cmdlet delle applicazioni di Call Park in base alle esigenze.
  
## <a name="emergency-calls"></a>Chiamate di emergenza
<a name="EmergencyCalls"> </a>

È necessario eseguire la procedura seguente per configurare i test di stress e prestazioni per le chiamate di emergenza:
  
1. Configurare una route vocale per le chiamate di emergenza. Puoi usare lo script RoutingRules. ps1 e selezionare il commento " **Route E911 to PSTN** " per un esempio di come configurare questa route vocale.
    
    > [!CAUTION]
    > Il comando di esempio in RoutingRules. ps1 contiene un modello di numero che include il numero 119 anziché 911. È consigliabile evitare di usare 911 (o il numero di emergenza locale effettivo) per evitare chiamate accidentali agli operatori di emergenza locali durante il test di carico. Tenere presente che questa configurazione è solo per scopi di simulazione. 
  
2. Configurare gli indirizzi compilando i valori della scheda **config del servizio informazioni sulla posizione** in UserProvisioningTool, come illustrato nella figura seguente:
    
     ![Strumento di provisioning degli utenti che mostra il numero di indirizzi, sottoreti, interruttori e porte.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Dopo aver immesso tutto nel UserProvisioningTool, fare clic sul pulsante **genera file di configurazione LIS** .
    
4. Ora vengono generati file CSV per porte, subnet, switch e punti di accesso wireless (WAP), oltre a un file XML per lo strumento stress e prestazioni. È possibile usare i file CSV per gli input quando si configura il servizio informazioni sulla posizione con lo script LisConfiguration. ps1. A tale scopo, è necessario trasferire il file Locations0. XML nella stessa cartella dello strumento eseguibile di stress e prestazioni (LyncPerfTool. exe). In questo modo si consente di eseguire gli scenari del profilo posizione (dial plan).
    
## <a name="configuring-response-group-application"></a>Configurazione dell'applicazione Response Group
<a name="ConfigResponseGroupApp"> </a>

Lo script di esempio è ResponseGroupConfiguration. ps1. Ci sono anche cmdlet di Response Group Application da rivedere per ulteriori dettagli sulla configurazione. Il diagramma seguente mostra alcuni dettagli della configurazione:
  
![Strumento di configurazione di Response Group che mostra i flussi di lavoro esistenti per i test.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

