---
title: Configurare CUCM per l'interoperabilità con Skype for Business Server
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
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: "Riepilogo: configurare LA GESTIONE risorse per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837116"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurare CUCM per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configurare la modalità DISA per l'utilizzo con Skype for Business Server.
  
> [!CAUTION]
> Questa funzionalità viene testata con Cisco Unified Communications Manager (CallManager, o CUCM) versione 10.5 utilizzando la configurazione trunk solo su TCP. Verificare che l'ambiente CUCM soddisfi questi criteri prima di procedere. 
  
Le impostazioni descritte di seguito sono solo esempi di come è possibile configurare la modalità di configurazione di CUCM per l'utilizzo con un VIS. Per ottenere lo stesso risultato, è possibile utilizzare anche altre impostazioni e/o utilizzi di funzionalità DISAS alternative. Non è consigliabile utilizzare la configurazione ottimale per uno scenario specifico.
  
Per l'interoperabilità con il VIS, è necessario confermare o modificare diverse impostazioni DIS. Seguire le procedure riportate di seguito per evitare la mancanza di impostazioni necessarie.
  
### <a name="configure-the-cucm"></a>Configurare il file CUCM

1. Accedere a CUCM e passare a Cisco Unified CM Administration- \> Call Routing- \> Class of Control- \> Partition.
    
2. Nella schermata Configurazione partizione immettere il nome e la descrizione della partizione e fare clic **su Aggiungi nuovo.**
    
3. Passare a Cisco Unified CM Administration- \> Call Routing- \> Class of Control- Calling Search \> Space.
    
4. Nella schermata Configurazione spazio di ricerca chiamante immettere il nome dello spazio di ricerca chiamante e in Partizioni selezionate immettere il nome della partizione appena creata. Al **termine,** fare clic su Salva.
    
5. Passare a Amministrazione cm unificato Cisco- Sistema- Sicurezza- Profilo di sicurezza \> \> trunk \> SIP.
    
6. Nella schermata Configurazione profilo di sicurezza trunk SIP impostare le opzioni relative alle informazioni del profilo di sicurezza trunk SIP come mostrato e fare clic su **Aggiungi nuovo.**
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modalità sicurezza dispositivo  <br/> |Non sicuro  <br/> |
   |Tipo di trasporto in ingresso  <br/> |TCP + UDP  <br/> |
   |Tipo di trasporto in uscita  <br/> |TCP  <br/> |
   |Porta in ingresso  <br/> |5060  <br/> |
   
7. Passare a Amministrazione CM unificato Cisco- \> Impostazioni dispositivo- \> Profilo \> SIP.
    
8. Nella schermata Configurazione profilo SIP impostare le opzioni relative alle informazioni sul profilo SIP come illustrato. 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrizione  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Nella stessa schermata, scorrere verso il basso fino alla sezione SDP Profile Information. L'opzione Modifica larghezza di banda a livello di sessione **SDP** per le offerte anticipate e i nuovi inviti è impostata per impostazione predefinita su TIAS e AS. Modificare questa opzione solo in TIAS. Se si lascia questa opzione all'impostazione predefinita, Skype for Business Server non comprenderà le informazioni sul modificatore della larghezza di banda nel messaggio SIP. TIAS means Transport Independent Application Specific while AS means Application Specific. Queste sono le opzioni SIP specificate in RFC3890.
    
10. Nella stessa schermata, scorrere ulteriormente verso il basso. Nella configurazione specifica del trunk del profilo SIP selezionare Supporto dell'offerta anticipata per le chiamate vocali e **video** e impostarlo sull'opzione Obbligatoria **(inserire MTP se necessario).** Ciò consentirà a CUCM di configurare una chiamata SIP in uscita con l'offerta anticipata. Una nuova funzionalità di CUCM 8.5 e oltre è che supporta la configurazione delle chiamate in uscita con l'offerta anticipata senza richiedere il punto di terminazione multimediale (MTP).
    
11. Verificare che nella sezione SIP Options ping la casella sia selezionata accanto a "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'".
    
12. Al termine, fare clic su **Aggiungi nuovo.**
    
13. Passare a Cisco Unified CM Administration- \> \> Device-Trunk. 
    
14. Impostare il protocollo del dispositivo su SIP e premere **Avanti.**
    
15. In Informazioni dispositivo imposta il nome e la descrizione del dispositivo (probabilmente su qualcosa come SfBVideoInterop_SIPTrunk) e imposta l'elenco dei gruppi di risorse multimediali su un MRGL che contiene le risorse multimediali giuste. 
    
16. Scorrere ulteriormente verso il basso. Il punto di terminazione multimediale (MTP) non è necessario per le videochiamate, se non è già deselezionato, deselezionalo. Seleziona l'opzione Esegui **su tutti i nodi CM unificati attivi.** Si noti che è necessario aggiungere tutti i nodi CUCM alla configurazione di Skype for Business Server.
    
17. Scorrere ulteriormente verso il basso. Impostare le opzioni Chiamate in ingresso e Impostazioni parte connessa come illustrato.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Chiamata dello spazio di ricerca  <br/> |CSS_SfBVideoInterop  <br/> |
    |Spazio di ricerca chiamate AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS trasformazione parte connessa  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scorrere ulteriormente verso il basso. Nella sezione Sip Information Destination della configurazione del trunk SIP specificare l'FQDN del pool VIS o l'indirizzo IP dei singoli server VIS nel pool (aggiungendo più voci). Nella porta di destinazione specificare la porta su cui VIS è in ascolto per le connessioni da CUCM (il valore predefinito è 6001). Specificare inoltre il profilo di sicurezza del trunk SIP e il profilo SIP creati in precedenza, come illustrato.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Profilo di sicurezza trunk SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Rerouting Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Subscribe Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |Profilo SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Metodo di segnalazione DTMF  <br/> |RFC 2833  <br/> |
   
19.  Scorrere ulteriormente verso il basso. Impostare le informazioni di registrazione in base alle esigenze del sistema. È possibile lasciarlo impostato su **Nessuno.** 
    
20. Al termine, fare clic su **Aggiungi nuovo.**
    
21. Passare a Cisco Unified CM Administration- \> Call Routing- \> Route/Hunt- \> Route pattern.
    
22. Nella schermata Configurazione motivo percorso immetti i parametri di definizione del modello mostrati di seguito. Scorrere verso il basso fino alla sezione Trasformazioni parti chiamate e impostare la maschera come mostrato, quindi fare clic **su Aggiungi nuovo** al termine dell'operazione.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Motivo percorso  <br/> |7779999  <br/> |
    |Partizione route  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrizione  <br/> |Partizione per SfBVideoInterop  <br/> |
    |Elenco gateway/route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Maschera di trasformazione parte chiamata  <br/> |+14257779999  <br/> |
   
23. Passare a Cisco Unified CM Administration- \> Call Routing- \> SIP Route Pattern.
    
24. Nella schermata Configurazione pattern route SIP impostare le opzioni di definizione del modello come mostrato e fare clic **su Aggiungi nuovo.**
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    | Utilizzo dei modelli <br/> |Routing del dominio  <br/> |
    |Modello IPv4  <br/> |contoso.com (lasciare vuoto se si utilizza IPv6)  <br/> |
    |Modello IPv6  <br/> |contoso.com (lasciare vuoto se si utilizza IPv4)  <br/> |
    |Descrizione  <br/> |Modello SIPRoute su mediarv  <br/> |
    |Partizione route  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Elenco trunk/route SIP  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Casella di controllo Motivo blocco  <br/> |lasciare deselezionata  <br/> |
   
25. Se sono state modificate le velocità in bit audio o video rispetto alle impostazioni predefinite, sarà necessario ripristinare le impostazioni predefinite. Per impostare la velocità in bit per le chiamate audio/video, passare ad Amministrazione CM unificato Cisco- \> System- \> Region Information- \> Region. Le impostazioni predefinite sono illustrate di seguito per riferimento:
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Area geografica  <br/> |Predefiniti  <br/> |
    |Elenco preferenze codec audio  <br/> |Impostazione predefinita di sistema  <br/> |
    |Velocità in bit audio massima  <br/> |64 kbps (G.722, G.711)  <br/> |
    |Velocità in bit massima sessione per videochiamate  <br/> |200000 kbps  <br/> |
    |Velocità in bit massima sessione  <br/> |2000000000 kbps  <br/> |
   
A questo punto il gateway video CUCM è configurato per l'utilizzo con vis. La configurazione corrispondente dovrà essere eseguita su ogni VTC che vuoi integrare.
> [!NOTE]
> Per migliorare la resilienza, è possibile configurare questo gateway CUCM per l'utilizzo con un secondo pool VIDEO Interop Server o VIS. Per [ulteriori informazioni, vedere Meccanismi](../../plan-your-deployment/video-interop-server.md#resiliency) di resilienza.
  
## <a name="see-also"></a>Vedere anche

[Configurare un VTC per l'interoperabilità con Skype for Business Server](configure-a-vtc-for-interoperation.md)
