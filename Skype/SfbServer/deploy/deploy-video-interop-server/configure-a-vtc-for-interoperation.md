---
title: Configurare un VTC per l'interoperabilità con Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: "Riepilogo: configurare i dispositivi VTC per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 1165b4bf569701d71a435a4162ef9feb9ef3018f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594680"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurare un VTC per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configurare i dispositivi VTC per l'utilizzo con Skype for Business Server.
  
Sarà necessario eseguire le procedure di personalizzazione della configurazione seguenti per ogni VTC che si connetterà al server VIS di Skype for Business tramite un trunk SIP e un gateway video Cisco Unified Communications Manager (CallManager o CUCM).
  
Le impostazioni descritte qui sono solo esempi di come cucm può essere configurato per l'utilizzo con un VIS. Per ottenere lo stesso risultato, è possibile utilizzare anche altre impostazioni e/o utilizzi della funzionalità CUCM alternativa. Non è consigliabile utilizzare la configurazione ottimale per uno scenario specifico.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurare un VTC registrato con CUCM

1. Accedi al dispositivo Cisco VTC e passa a Configurazione- \> Configurazione di sistema- \> Provisioning.
    
2. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità provisioning  <br/> | CUCM <br/> |
   |ExternalManager Address  <br/> | FQDN di CUCM <br/> |
   | ExternalManager Domain <br/> |Dominio di CUCM  <br/> |
   
3. Passare a Configurazione- \> Configurazione di sistema- \> Rete.
    
4. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome di dominio DNS  <br/> | Nome di dominio di CUCM <br/> |
   |Indirizzo server DNS 1  <br/> | l'indirizzo del server DNS desiderato <br/> |
   
5. Passare a Configurazione- \> Configurazione di sistema- \> Servizi di rete. Verificare che la modalità H.323 sia disattivata e che la modalità SIP sia attivata. 
    
6. Queste opzioni vengono impostate automaticamente quando l'endpoint viene registrato con CUCM. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità H.323  <br/> | Disattivato <br/> |
   |Modalità HTTP  <br/> | Attivato <br/> |
   | Modalità SIP <br/> | Attivato <br/> |
   |Modalità Telnet  <br/> | Attivato <br/> |
   |WelcomeText  <br/> | Attivato <br/> |
   |Modalità XMLAPI  <br/> | Attivato <br/> |
   
7. Passare a Configurazione- \> Configurazione di sistema- \> SIP.
    
8. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Profilo 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profilo 1 - In uscita  <br/> | Disattivato <br/> |
   |Profilo 1 - TlsVerify  <br/> | Attivato <br/> |
   |Profilo 1 - Tipo  <br/> | Cisco <br/> |
   |Profilo 1 - URI  <br/> | Assegnato automaticamente alla registrazione CUCM <br/> |
   |Proxy 1 - Indirizzo  <br/> |Nome host del cucm  <br/> |
   
Il VTC è ora configurato per l'interoperabilità. Prima che il servizio possa iniziare, è necessario eseguire i passaggi finali sul lato CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurare i dispositivi VTC in CUCM

1. Accedere a CUCM e passare a Cisco Unified CM Administration- \> Device- \> Telefono- \> Find. 
    
2. Selezionare il dispositivo VTC da configurare. Verificare le impostazioni seguenti nella schermata Telefono configurazione, correggendo in base alle esigenze. Dopo aver modificato o verificato queste impostazioni, fare clic su **Salva.**
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Informazioni dispositivo - modello Telefono pulsante  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |Informazioni sul dispositivo - Profilo Telefono comune  <br/> | Standard Common Telefono Profile <br/> |
   |Informazioni sul dispositivo - Spazio di ricerca chiamante  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni dispositivo - Spazio di ricerca chiamate AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni dispositivo - Elenco gruppi di risorse multimediali  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo - Profilo di sicurezza del dispositivo  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Informazioni specifiche del protocollo - Rerouting Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo - SUBSCRIBE Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo -Profilo SIP  <br/> | Profilo SIP standard per endpoint di telepresenza <br/> |
   
3. Dopo aver salvato la configurazione VTC, torna alla schermata Telefono configurazione del dispositivo. Nella parte superiore della schermata del gruppo Associazione fai clic sull'associazione per l'interoperabilità video. Verrà visualizzata la schermata Configurazione numero di directory. 
    
4. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
    Apportare le modifiche appropriate come indicato nelle informazioni sul numero di directory e sul numero di Impostazioni.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   | Informazioni sul numero di directory - Partizione route <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Directory Number Impostazioni - Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |MlPP Alternate Party and Confidential Access Level Impostazioni - MlPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Riga 1 nel dispositivo - Display (ID chiamante)  <br/> | Come desiderato <br/> |
   |Riga 1 nel dispositivo - Visualizzazione ASCII (ID chiamante)  <br/> | Come desiderato <br/> |
   
5. Al termine, scorrere fino alla parte superiore dello schermo e premere **Salva.** 
    
La configurazione è stata completata per questo dispositivo VTC. Dovrai ripetere questo processo per altri dispositivi VTC nella tua azienda.

