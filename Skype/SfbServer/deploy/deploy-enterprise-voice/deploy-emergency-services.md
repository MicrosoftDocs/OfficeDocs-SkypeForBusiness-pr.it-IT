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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Distribuire il servizio E9-1-1 in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812526"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Distribuire i servizi di emergenza in Skype for Business Server
 
Distribuire il servizio E9-1-1 in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
  
Enhanced 9-1-1 (E9-1-1) è una funzionalità di notifica di emergenza che associa il numero di telefono della parte chiamante a una civica o a un indirizzo di strada. Con tali informazioni, l'operatore del servizio di salute pubblica e sicurezza nazionale (PSAP) è in grado di erogare immediatamente servizi di emergenza nei confronti del chiamante in difficoltà.
  
Per supportare il servizio E9-1-1, Skype for Business Server deve essere in grado di associare correttamente una posizione a un client e di verificare che queste informazioni siano utilizzate per instradare la chiamata di emergenza al PSAP più vicino.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Prerequisiti per la distribuzione di E9-1-1

Prima di distribuire il servizio E9-1-1, è necessario che siano già stati distribuiti i server interni di Skype for Business Server, tra cui un archivio di gestione centrale, un pool Front end o un server Standard Edition. È inoltre necessario distribuire uno o più Mediation Server, indipendenti o collocati con Front End Server. Inoltre, una distribuzione di E9-1-1 richiede un trunk SIP a un provider di servizi E9-1-1 qualificato o a un gateway ELIN (Emergency Location Identification Number) per la rete PSTN (Public Switched Telephone Network).
  
## <a name="deployment-process"></a>Processo di distribuzione

Nella tabella seguente viene fornita una panoramica del processo di distribuzione di E9-1-1.
  
|**Fase**|**Procedura**|**Ruoli**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare gli utilizzi vocali, le route e le configurazioni trunk  <br/> |1. creare un nuovo record di utilizzo PSTN. Si tratta dello stesso nome utilizzato per l'impostazione di **utilizzo PSTN** nei criteri percorso. <br/> 2. creare o assegnare una route vocale al record di utilizzo PSTN creato nel passaggio precedente e quindi fare in modo che l'attributo del gateway punti al trunk SIP E9-1-1 o al gateway ELIN.  <br/> 3. per un provider di servizi E9-1-1 trunk SIP, impostare il trunk che gestirà le chiamate E9-1-1 sul SIP per passare i dati di PIDF-LO utilizzando il cmdlet **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. Facoltativamente, per un provider di servizi E9-1-1 trunk SIP, creare o assegnare una route PSTN locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile. Se supportato dal provider di servizi E9-1-1, assegnare una regola di configurazione trunk al gateway che converte la stringa di composizione 911 nel numero DID (Direct Inward Dialing) del National/Regional Emergency Call Response Center (ECRC).  <br/> |CSVoiceAdmin  <br/> |[Configurare una route vocale E9-1-1 in Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Creare criteri percorso e assegnarli a utenti e subnet  <br/> |1. esaminare il criterio percorso globale.  <br/> 2. creare un criterio percorso con un ambito a livello di utente. in alternativa, se l'organizzazione dispone di più siti con usi di emergenza diversi, creare un criterio percorso con un ambito a livello di rete.  <br/> 3. assegnare il criterio percorso ai siti di rete.  <br/> 4. aggiungere le subnet appropriate al sito di rete.  <br/> 5. (facoltativo) assegnare il criterio percorso ai criteri utente.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (eccetto per la creazione di criteri percorso)  <br/> |[Creare criteri percorso in Skype for Business Server](create-location-policies.md) <br/> [Aggiungere un criterio percorso a un sito di rete in Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurare il database di percorso  <br/> |1. popolare il database con un mapping degli elementi di rete in percorsi.  <br/> 2. per i gateway ELIN, aggiungere i numeri ELIN alla \<CompanyName\> colonna.  <br/> 3. configurare la connessione al provider di servizi E9-1-1 per la convalida degli indirizzi.  <br/> 4. convalidare gli indirizzi con il provider di servizi E9-1-1.  <br/> 5. pubblicare il database aggiornato.  <br/> 6. per i gateway ELIN, caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurare il database delle posizioni in Skype for Business Server](configure-the-location-database.md) <br/> |
|Configurare le funzionalità avanzate (facoltativo)  <br/> |1. configurare l'URL per l'applicazione SNMP.  <br/> 2. configurare l'URL per la posizione del servizio informazioni percorso secondario.  <br/> |CSVoiceAdmin  <br/> |[Configurare un'applicazione SNMP in Skype for Business Server](configure-an-snmp-application.md) <br/> [Configurare un servizio informazioni percorso secondario in Skype for Business Server](secondary-location-information-service.md) <br/> |
   

