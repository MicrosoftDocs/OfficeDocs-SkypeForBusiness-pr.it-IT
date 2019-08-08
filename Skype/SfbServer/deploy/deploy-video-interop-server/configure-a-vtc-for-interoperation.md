---
title: Configurare un VTC per l'interoperabilità con Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: "Riepilogo: configurare i dispositivi VTC per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 8c5310479aea38f5623f8ac2e10ef64978aa4aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235672"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurare un VTC per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configurare i dispositivi VTC per l'utilizzo con Skype for Business Server.
  
Dovrai eseguire le procedure di personalizzazione di configurazione seguenti per ogni VTC che si connette al server VIS Skype for business tramite un trunk SIP e un gateway video Cisco Unified Communications Manager (CallManager o CUCM).
  
Le impostazioni descritte in questo articolo sono intese solo come esempi di come CUCM può essere configurato per l'utilizzo con un VIS. Altre impostazioni e/o usi della funzionalità CUCM alternativa possono essere usati anche per ottenere lo stesso risultato. Nessuna raccomandazione è implicita sulla configurazione ottimale per uno scenario specifico.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurare un VTC registrato con CUCM

1. Accedere al dispositivo Cisco VTC e passare a configurazione-\>configurazione di sistema-\>provisioning.
    
2. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità di provisioning  <br/> | CUCM <br/> |
   |Indirizzo ExternalManager  <br/> | Nome di dominio completo di CUCM <br/> |
   | Dominio ExternalManager <br/> |Dominio di CUCM  <br/> |
   
3. Passare a configurazione-\>configurazione di sistema\>-rete.
    
4. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome di dominio DNS  <br/> | Nome di dominio di CUCM <br/> |
   |Indirizzo del server DNS 1  <br/> | Indirizzo del server DNS desiderato <br/> |
   
5. Passare a configurazione-\>configurazione di sistema\>-servizi di rete. Verificare che la modalità H. 323 sia disattivata e che la modalità SIP sia attivata. 
    
6. Queste opzioni vengono impostate automaticamente quando l'endpoint viene registrato con CUCM. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Modalità H. 323  <br/> | Disattivare <br/> |
   |Modalità HTTP  <br/> | Nella <br/> |
   | Modalità SIP <br/> | Nella <br/> |
   |Modalità Telnet  <br/> | Nella <br/> |
   |WelcomeText  <br/> | Nella <br/> |
   |Modalità XMLAPI  <br/> | Nella <br/> |
   
7. Passare a configurazione-\>configurazione di sistema\>-SIP.
    
8. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Profilo 1-DefaultTransport  <br/> | TCP <br/> |
   |Profilo 1-in uscita  <br/> | Disattivare <br/> |
   |Profilo 1-TlsVerify  <br/> | Nella <br/> |
   |Profilo 1-tipo  <br/> | Cisco <br/> |
   |Profilo 1-URI  <br/> | Assegnato automaticamente alla registrazione di CUCM <br/> |
   |Indirizzo proxy 1  <br/> |Nome host della CUCM  <br/> |
   
VTC è ora configurato per l'interoperabilità. Prima che il servizio possa iniziare, ci sono passaggi finali da eseguire sul lato CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurare i dispositivi VTC in CUCM

1. Accedere a CUCM e passare a Cisco Unified CM Administration-\>Device-\>Phone-\>Find. 
    
2. Selezionare il dispositivo VTC da configurare. Verificare le impostazioni seguenti nella schermata Configurazione Telefono, correggendo le esigenze. Dopo aver modificato o verificato le impostazioni, fare clic su **Salva**.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Informazioni sul dispositivo-modello di pulsante telefono  <br/> | Standard Cisco TelePresence codec C40 <br/> |
   |Informazioni sul dispositivo-profilo del telefono comune  <br/> | Profilo di telefono comune standard <br/> |
   |Informazioni sul dispositivo: spazio di ricerca chiamante  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni sul dispositivo-area di ricerca chiamata AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni sul dispositivo-elenco gruppi risorse multimediali  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informazioni specifiche sul protocollo-profilo di sicurezza del dispositivo  <br/> | Cisco telepresenza codec C40 <br/> |
   |Informazioni specifiche del protocollo-reinstradamento delle chiamate nello spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche per il protocollo-sottoscrivere lo spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Informazioni specifiche sul protocollo-profilo SIP  <br/> | Profilo SIP standard per endpoint telepresenza <br/> |
   
3. Dopo aver salvato la configurazione di VTC, passare di nuovo alla schermata di configurazione del telefono per il dispositivo. Nella parte superiore della schermata del gruppo associazione fare clic sull'associazione per l'interoperabilità video. Viene visualizzata la schermata di configurazione del numero di directory. 
    
4. Verificare le impostazioni seguenti, correggendo in base alle esigenze: 
    
    Apportare le modifiche appropriate come mostrato alle informazioni relative al numero di directory e alle impostazioni del numero di directory.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   | Informazioni sul numero di directory-route Partition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Impostazioni numero directory-chiamata dello spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Impostazioni del livello di accesso riservato e del partito alternativo MLPP-MLPP chiamata dello spazio di ricerca  <br/> | CSS_SfBVideoInterop <br/> |
   |Linea 1 su Device-display (ID chiamante)  <br/> | Come desiderato <br/> |
   |Riga 1 sul dispositivo-visualizzazione ASCII (ID chiamante)  <br/> | Come desiderato <br/> |
   
5. Al termine, scorrere fino all'inizio dello schermo e premere **Salva**. 
    
La configurazione è ora completa per questo dispositivo VTC. Sarà necessario ripetere questa procedura per gli altri dispositivi VTC dell'organizzazione.

