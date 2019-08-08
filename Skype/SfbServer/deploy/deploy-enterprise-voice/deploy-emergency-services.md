---
title: Distribuire servizi di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Distribuire E9-1-1 in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo processo di distribuzione.
ms.openlocfilehash: a96d425f39b53c970047eb220e0ae9f61b515089
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233511"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Distribuire servizi di emergenza in Skype for Business Server
 
Distribuire E9-1-1 in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo processo di distribuzione.
  
Enhanced 9-1-1 (E9-1-1) è una funzionalità di notifica di emergenza che associa il numero di telefono della parte chiamante a un indirizzo civico o stradale. Usando queste informazioni, il PSAP (Public Safety Answering Point) può immediatamente inviare i servizi di emergenza al chiamante in difficoltà.
  
Per supportare E9-1-1, Skype for Business Server deve essere in grado di associare correttamente una posizione a un client e verificare che queste informazioni vengano usate per instradare la chiamata di emergenza al PSAP più vicino.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Prerequisiti di distribuzione per E9-1-1

Prima di distribuire E9-1-1, è necessario che siano già stati distribuiti i server interni di Skype for Business Server, incluso un Central Management store, un pool Front end o un server Standard Edition. È inoltre necessario distribuire uno o più server di mediazione, autonomi o collocati con i server front-end. Inoltre, una distribuzione di E9-1-1 richiede un trunk SIP per un provider di servizi E9-1-1 qualificato o un gateway ELIN (Emergency Location Identification Number) per la rete PSTN (Public Switched Telephone Network).
  
## <a name="deployment-process"></a>Processo di distribuzione

La tabella seguente offre una panoramica del processo di distribuzione di E9-1-1.
  
|**Fase**|**Passaggi**|**Ruoli**|**Documentazione di distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare l'utilizzo delle voci, le rotte e le configurazioni trunk  <br/> |1. creare un nuovo record di utilizzo PSTN. Si tratta dello stesso nome usato per l'impostazione **utilizzo PSTN** nei criteri posizione. <br/> 2. creare o assegnare una route vocale al record di utilizzo PSTN creato nel passaggio precedente e quindi posizionare l'attributo gateway sul trunk SIP E9-1-1 o sul gateway ELIN.  <br/> 3. per un provider di servizi E9-1-1 trunk SIP, imposta il trunk che gestirà le chiamate E9-1-1 tramite il SIP per passare i dati di PIDF-LO usando il cmdlet **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. Facoltativamente, per un provider di servizi E9-1-1 trunk SIP, creare o assegnare una route PSTN locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà usata se la connessione al provider di servizi E9-1-1 non è disponibile. Se supportata dal provider di servizi E9-1-1, assegna una regola di configurazione trunk al gateway che converte la stringa di chiamata di 911 nel numero di chiamata diretta (DID) del centro di risposta alle chiamate di emergenza nazionali/regionali (ECRC).  <br/> |CSVoiceAdmin  <br/> |[Configurare una route vocale E9-1-1 in Skype for Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Creare criteri di posizione e assegnarli a utenti e subnet  <br/> |1. esaminare il criterio della posizione globale.  <br/> 2. creare un criterio di posizione con un ambito a livello di utente; in alternativa, se l'organizzazione ha più di un sito con diversi usi di emergenza, crea un criterio di posizione con un ambito a livello di rete.  <br/> 3. assegnare i criteri di posizione ai siti di rete.  <br/> 4. aggiungere le subnet appropriate al sito di rete.  <br/> 5. (facoltativo) assegnare i criteri di posizione ai criteri per gli utenti.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (ad eccezione della creazione di criteri di posizione)  <br/> |[Creare criteri di posizione in Skype for Business Server](create-location-policies.md) <br/> [Aggiungere un criterio di posizione a un sito di rete in Skype for Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurare il database della posizione  <br/> |1. compilare il database con un mapping degli elementi di rete alle posizioni.  <br/> 2. per i gateway ELIN, aggiungere i numeri ELIN alla colonna \<CompanyName\> .  <br/> 3. configurare la connessione al provider di servizi E9-1-1 per la convalida degli indirizzi.  <br/> 4. convalidare gli indirizzi con il provider di servizi E9-1-1.  <br/> 5. pubblicare il database aggiornato.  <br/> 6. per i gateway ELIN, caricare i numeri ELIN nel database di identificazione automatica della posizione (ALI) del gestore PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurare il database della posizione in Skype for Business Server](configure-the-location-database.md) <br/> |
|Configurare le funzionalità avanzate (facoltativo)  <br/> |1. configurare l'URL per l'applicazione SNMP.  <br/> 2. configurare l'URL per la posizione del servizio informazioni sulla posizione secondaria.  <br/> |CSVoiceAdmin  <br/> |[Configurare un'applicazione SNMP in Skype for Business Server](configure-an-snmp-application.md) <br/> [Configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server](secondary-location-information-service.md) <br/> |
   

