---
title: Distribuire i servizi di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Distribuire E9-1-1 in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
ms.openlocfilehash: 51c877fd285bd9db31de697e72458a44d44d0b71
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600711"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Distribuire i servizi di emergenza in Skype for Business Server
 
Distribuire E9-1-1 in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
  
Enhanced 9-1-1 (E9-1-1) è una funzionalità di notifica di emergenza che associa il numero di telefono della parte chiamante a un civico o a un indirizzo stradale. Con tali informazioni, l'operatore del servizio di salute pubblica e sicurezza nazionale (PSAP) è in grado di erogare immediatamente servizi di emergenza nei confronti del chiamante in difficoltà.
  
Per supportare E9-1-1, Skype for Business Server deve essere in grado di associare correttamente una posizione a un client e di assicurarsi che queste informazioni vengano utilizzate per instradare la chiamata di emergenza al PSAP più vicino.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Prerequisiti di distribuzione per E9-1-1

Prima di distribuire E9-1-1, è necessario aver già distribuito i server interni di Skype for Business Server, tra cui un archivio di gestione centrale, un pool Front End o un server edizione Standard. È inoltre necessario distribuire uno o più Mediation Server, autonomi o collocati con Front End Server. Inoltre, una distribuzione E9-1-1 richiede un trunk SIP a un provider di servizi E9-1-1 qualificato o un gateway ELIN (Emergency Location Identification Number) alla rete PSTN (Public Switched Telephone Network).
  
## <a name="deployment-process"></a>Processo di distribuzione

Nella tabella seguente viene fornita una panoramica del processo di distribuzione di E9-1-1.
  
|**Fase**|**Procedura**|**Ruoli**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare utilizzi vocali, route e configurazioni trunk  <br/> |1. Creare un nuovo record di utilizzo PSTN. Questo è lo stesso nome utilizzato per l'impostazione **Utilizzo PSTN** nel criterio percorso. <br/> 2. Creare o assegnare una route vocale al record di utilizzo PSTN creato nel passaggio precedente e quindi puntare l'attributo gateway al trunk SIP o al gateway ELIN E9-1-1.  <br/> 3. Per un provider di servizi E9-1-1 trunk SIP, impostare il trunk che gestirà le chiamate E9-1-1 su SIP per passare i dati PIDF-LO utilizzando il cmdlet **Set-CsTrunkConfiguration -EnablePIDFLOSupport.** <br/> 4. Facoltativamente, per un provider di servizi E9-1-1 trunk SIP, creare o assegnare una route PSTN locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile. Se supportato dal provider di servizi E9-1-1, assegnare una regola di configurazione trunk al gateway che converte la stringa di composizione 911 nel numero DID (Direct Inward Dialing) del centro ECRC (Emergency Call Response Center) nazionale/regionale.  <br/> |CSVoiceAdmin  <br/> |[Configurare una route vocale E9-1-1 in Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Creare criteri percorso e assegnarli a utenti e subnet  <br/> |1. Esaminare i criteri percorso globali.  <br/> 2. Creare un criterio percorso con un ambito a livello di utente; oppure, se l'organizzazione dispone di più siti con utilizzi di emergenza diversi, creare un criterio percorso con un ambito a livello di rete.  <br/> 3. Assegnare il criterio percorso ai siti di rete.  <br/> 4. Aggiungere le subnet appropriate al sito di rete.  <br/> 5. (Facoltativo) Assegnare i criteri percorso ai criteri utente.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (ad eccezione della creazione di criteri percorso)  <br/> |[Creare criteri percorso in Skype for Business Server](create-location-policies.md) <br/> [Aggiungere un criterio percorso a un sito di rete in Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurare il database di percorso  <br/> |1. Popolare il database con un mapping di elementi di rete a posizioni.  <br/> 2. Per i gateway ELIN, aggiungere gli ELAN alla \<CompanyName\> colonna.  <br/> 3. Configurare la connessione al provider di servizi E9-1-1 per la convalida degli indirizzi.  <br/> 4. Convalidare gli indirizzi con il provider di servizi E9-1-1.  <br/> 5. Pubblicare il database aggiornato.  <br/> 6. Per i gateway ELIN, caricare gli ELIN nel database ALI (Automatic Location Identification) del gestore PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurare il database delle località in Skype for Business Server](configure-the-location-database.md) <br/> |
|Configurare le funzionalità avanzate (facoltativo)  <br/> |1. Configurare l'URL per l'applicazione SNMP.  <br/> 2. Configurare l'URL per il percorso del servizio Informazioni percorso secondario.  <br/> |CSVoiceAdmin  <br/> |[Configurare un'applicazione SNMP in Skype for Business Server](configure-an-snmp-application.md) <br/> [Configurare un servizio informazioni percorso secondario in Skype for Business Server](secondary-location-information-service.md) <br/> |
   

