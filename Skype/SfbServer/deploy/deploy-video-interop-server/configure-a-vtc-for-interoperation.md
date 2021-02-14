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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: "Riepilogo: configurare i dispositivi VTC per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802076"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurare un VTC per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configurare i dispositivi VTC per l'utilizzo con Skype for Business Server.
  
Dovrai eseguire le seguenti procedure di personalizzazione della configurazione per ogni VTC che si connetterà al server Skype for Business VIS tramite un trunk SIP e un gateway video Cisco Unified Communications Manager (CallManager o CUCM).
  
Le impostazioni descritte di seguito sono solo esempi di come è possibile configurare la modalità di configurazione di CUCM per l'utilizzo con un VIS. Per ottenere lo stesso risultato, è possibile utilizzare anche altre impostazioni e/o utilizzi di funzionalità DISAS alternative. Non è consigliabile utilizzare la configurazione ottimale per uno scenario specifico.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurare un VTC registrato con CUCM

1. Accedi al dispositivo VTC Cisco e passa a Configurazione- \> Configurazione del sistema- \> Provisioning.
    
2. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità di provisioning  <br/> | CUCM <br/> |
   |Indirizzo ExternalManager  <br/> | FQDN di CUCM <br/> |
   | Dominio ExternalManager <br/> |Dominio di CUCM  <br/> |
   
3. Passare a Configurazione- \> Configurazione di sistema- \> Rete.
    
4. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome di dominio DNS  <br/> | Nome di dominio di CUCM <br/> |
   |Indirizzo server DNS 1  <br/> | l'indirizzo del server DNS desiderato <br/> |
   
5. Passare a Configurazione- \> Configurazione di sistema - Servizi di \> rete. Verificare che la modalità H.323 sia disattivata e che la modalità SIP sia attivata. 
    
6. Queste opzioni vengono impostate automaticamente quando l'endpoint viene registrato con CUCM. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità H.323  <br/> | Off <br/> |
   |Modalità HTTP  <br/> | Attivato <br/> |
   | Modalità SIP <br/> | Attivato <br/> |
   |Modalità Telnet  <br/> | Attivato <br/> |
   |WelcomeText  <br/> | Attivato <br/> |
   |Modalità XMLAPI  <br/> | Attivato <br/> |
   
7. Passare a Configurazione- \> Configurazione sistema- \> SIP.
    
8. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Profilo 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profilo 1 - In uscita  <br/> | Off <br/> |
   |Profilo 1 - TlsVerify  <br/> | Attivato <br/> |
   |Profilo 1 - Tipo  <br/> | Cisco <br/> |
   |Profilo 1 - URI  <br/> | Assegnato automaticamente alla registrazione DISAS <br/> |
   |Proxy 1 - Indirizzo  <br/> |Il nome host di CUCM  <br/> |
   
I VTC sono ora configurati per l'interoperabilità. Prima che il servizio possa iniziare, è necessario eseguire i passaggi finali sul lato DISS.
### <a name="configure-vtc-devices-on-cucm"></a>Configurare i dispositivi VTC in CUCM

1. Accedi a CUCM e passa ad Amministrazione CM unificato Cisco- \> Dispositivo- \> Telefono- \> Trova. 
    
2. Seleziona il dispositivo VTC da configurare. Verificare le impostazioni seguenti nella schermata Configurazione telefono, correggendo in base alle esigenze. Dopo aver modificato o verificato queste impostazioni, fare clic su **Salva.**
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Device Information - Phone Button Template  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |Informazioni dispositivo - Profilo telefono comune  <br/> | Profilo telefonico comune standard <br/> |
   |Informazioni dispositivo - Spazio di ricerca chiamate  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni dispositivo - Spazio di ricerca chiamate AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni dispositivo - Elenco gruppi di risorse multimediali  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo - Profilo di sicurezza del dispositivo  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Informazioni specifiche del protocollo - Rerouting Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo - SUBSCRIBE Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche del protocollo -Profilo SIP  <br/> | Profilo SIP standard per endpoint di telepresenza <br/> |
   
3. Dopo aver salvato la configurazione VTC, torna alla schermata Configurazione telefono per il dispositivo. At the top of the screen in the Association group, click on the association for the Video Interop. Verrà visualizzata la schermata Configurazione numero di directory. 
    
4. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
    Apportare le modifiche appropriate come mostrato in Informazioni numero directory e Impostazioni numero directory.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   | Informazioni sul numero di directory - Partizione route <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Impostazioni numero directory - Spazio di ricerca chiamante  <br/> | CSS_SfBVideoInterop <br/> |
   |Impostazioni del livello di accesso riservato e della parte alternativa MLPP - Spazio di ricerca chiamate MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Riga 1 nel dispositivo - Schermo (ID chiamante)  <br/> | Come desiderato <br/> |
   |Riga 1 nel dispositivo - Visualizzazione ASCII (ID chiamante)  <br/> | Come desiderato <br/> |
   
5. Al termine, scorrere fino alla parte superiore dello schermo e premere **Salva.** 
    
La configurazione è ora completa per questo dispositivo VTC. Dovrai ripetere questo processo per altri dispositivi VTC nell'organizzazione.

