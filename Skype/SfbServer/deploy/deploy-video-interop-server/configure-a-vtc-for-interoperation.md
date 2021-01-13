---
title: Configurare un videoconferenza per l'interoperabilità con Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: "Riepilogo: configurare i dispositivi di videoconferenza per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802076"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurare un videoconferenza per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configurare i dispositivi di videoconferenza per l'utilizzo con Skype for Business Server.
  
Sarà necessario eseguire le procedure di personalizzazione di configurazione seguenti per ogni videoconferenza che si connette a Skype for Business Server tramite un trunk SIP e un gateway video di Cisco Unified Communications Manager (CallManager o un CUCM).
  
Le impostazioni descritte in questa sezione sono intese solo come esempi di come un CUCM può essere configurato per l'utilizzo con un VIS. È inoltre possibile utilizzare altre impostazioni e/o usi della funzionalità un CUCM alternativa per ottenere lo stesso risultato. Nessuna raccomandazione è implicita sulla configurazione ottimale per uno scenario specifico.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurare un videoconferenza registrato con un CUCM

1. Accedere al dispositivo Cisco videoconferenza e passare a configurazione-sistema di configurazione \> - \> provisioning.
    
2. Verificare le impostazioni seguenti, correggendo i valori necessari: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità di provisioning  <br/> | UN CUCM <br/> |
   |Indirizzo ExternalManager  <br/> | FQDN di un CUCM <br/> |
   | Dominio ExternalManager <br/> |Dominio di un CUCM  <br/> |
   
3. Accedere a configurazione- \> sistema di configurazione- \> rete.
    
4. Verificare le impostazioni seguenti, correggendo i valori necessari: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome di dominio DNS  <br/> | Nome di dominio di un CUCM <br/> |
   |Indirizzo del server DNS 1  <br/> | l'indirizzo del server DNS desiderato <br/> |
   
5. Accedere a configurazione- \> sistema di configurazione- \> servizi di rete. Verificare che la modalità H. 323 sia disattivata e che la modalità SIP sia attivata. 
    
6. Queste opzioni vengono impostate automaticamente quando l'endpoint è registrato con un CUCM. Verificare le impostazioni seguenti, correggendo i valori necessari: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità H. 323  <br/> | Off <br/> |
   |Modalità HTTP  <br/> | Attivato <br/> |
   | Modalità SIP <br/> | Attivato <br/> |
   |Modalità Telnet  <br/> | Attivato <br/> |
   |WelcomeText  <br/> | Attivato <br/> |
   |Modalità XMLAPI  <br/> | Attivato <br/> |
   
7. Passare a configurazione- \> sistema di configurazione- \> SIP.
    
8. Verificare le impostazioni seguenti, correggendo i valori necessari: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Profile 1-DefaultTransport  <br/> | TCP <br/> |
   |Profilo 1-in uscita  <br/> | Off <br/> |
   |Profile 1-TlsVerify  <br/> | Attivato <br/> |
   |Profilo 1-tipo  <br/> | Cisco <br/> |
   |Profilo 1-URI  <br/> | Assegnato automaticamente alla registrazione di un CUCM <br/> |
   |Proxy 1-indirizzo  <br/> |Il nome host del un CUCM  <br/> |
   
La videoconferenza è ora configurata per l'interoperabilità. Prima dell'inizio del servizio, è possibile eseguire le operazioni finali sul un CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurare i dispositivi di videoconferenza in un CUCM

1. Accedere a un CUCM e accedere a Cisco Unified CM Administration- \> Device- \> Phone- \> Find. 
    
2. Selezionare il dispositivo di videoconferenza da configurare. Verificare le impostazioni seguenti nella schermata Configurazione Telefono, correggendo in base alle esigenze. Dopo aver modificato o verificato queste impostazioni, fare clic su **Salva**.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Informazioni sul dispositivo-modello di pulsante del telefono  <br/> | Codec di telepresenza Cisco standard C40 <br/> |
   |Informazioni sul dispositivo-profilo comune del telefono  <br/> | Profilo standard per i telefoni comuni <br/> |
   |Informazioni sul dispositivo-spazio di ricerca di chiamata  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni sui dispositivi-AAR che chiama lo spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni sul dispositivo-elenco dei gruppi di risorse multimediali  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo-profilo di sicurezza del dispositivo  <br/> | Codec di telepresenza Cisco C40 <br/> |
   |Informazioni specifiche del protocollo-rerouting delle chiamate nello spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo-SUBSCRIBE Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo-profilo SIP  <br/> | Profilo SIP standard per endpoint di telepresenza <br/> |
   
3. Dopo aver salvato la configurazione di videoconferenza, passare alla schermata di configurazione del telefono per il dispositivo. Nella parte superiore dello schermo del gruppo di associazione fare clic sull'associazione per l'interoperabilità video. Viene visualizzata la schermata di configurazione del numero di directory. 
    
4. Verificare le impostazioni seguenti, correggendo i valori necessari: 
    
    Apportare le modifiche appropriate come mostrato alle informazioni sul numero di directory e le impostazioni dei numeri di directory.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   | Informazioni sul numero di directory-route Partition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Impostazioni del numero di directory-chiamata dello spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Impostazioni di MLPP Party alternativo e livello di accesso riservato-MLPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Riga 1 del dispositivo-visualizzazione (ID chiamante)  <br/> | Come desiderato <br/> |
   |Riga 1 del dispositivo-visualizzazione ASCII (ID chiamante)  <br/> | Come desiderato <br/> |
   
5. Al termine, scorrere fino alla parte superiore dello schermo e premere **Salva**. 
    
La configurazione è ora completata per il dispositivo videoconferenza. Sarà necessario ripetere questa procedura per gli altri dispositivi di videoconferenza nell'organizzazione.

