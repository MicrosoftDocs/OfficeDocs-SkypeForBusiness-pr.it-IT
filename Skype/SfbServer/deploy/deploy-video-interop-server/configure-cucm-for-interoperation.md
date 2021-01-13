---
title: Configurare un CUCM per l'interoperabilità con Skype for Business Server
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
description: "Riepilogo: configurare un CUCM per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837116"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurare un CUCM per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configurare un CUCM per l'utilizzo con Skype for Business Server.
  
> [!CAUTION]
> Questa funzionalità viene testata con Cisco Unified Communications Manager (CallManager o un CUCM) versione 10,5 utilizzando Trunks setup su TCP solo. Verificare che l'ambiente un CUCM soddisfi questi criteri prima di continuare. 
  
Le impostazioni descritte in questa sezione sono intese solo come esempi di come un CUCM può essere configurato per l'utilizzo con un VIS. È inoltre possibile utilizzare altre impostazioni e/o usi della funzionalità un CUCM alternativa per ottenere lo stesso risultato. Nessuna raccomandazione è implicita sulla configurazione ottimale per uno scenario specifico.
  
Per l'interoperabilità con il VIS è necessario confermare o modificare una serie di impostazioni di un CUCM. Seguire le procedure riportate di seguito per evitare che vengano perse le impostazioni necessarie.
  
### <a name="configure-the-cucm"></a>Configurare un CUCM

1. Accedere a un CUCM e passare a Cisco Unified CM Administration- \> call routing- \> Class of Control- \> Partition.
    
2. Nella schermata configurazione partizione, immettere il nome e la descrizione della partizione e fare clic su **Aggiungi nuovo**.
    
3. Passare a Cisco Unified CM Administration- \> call routing- \> Class of Control-Calling \> Search Space.
    
4. Nella schermata di configurazione dello spazio di ricerca chiamante, immettere il nome per lo spazio di ricerca chiamante e, in partizioni selezionate, immettere il nome della partizione appena creata. Fare clic su **Salva** al termine.
    
5. Passare a Cisco Unified CM Administration- \> System- \> Security- \> SIP trunk Security Profile.
    
6. Nella schermata Configurazione profilo di sicurezza trunk SIP impostare le opzioni di informazioni sul profilo di sicurezza trunk SIP come illustrato e quindi fare clic su **Aggiungi nuovo**.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modalità di sicurezza del dispositivo  <br/> |Non protetto  <br/> |
   |Tipo di trasporto in ingresso  <br/> |TCP + UDP  <br/> |
   |Tipo di trasporto in uscita  <br/> |TCP  <br/> |
   |Porta in ingresso  <br/> |5060  <br/> |
   
7. Accedere a Cisco Unified CM Administration-impostazioni dispositivo-dispositivo- \> \> \> profilo SIP.
    
8. Nella schermata Configurazione profilo SIP impostare le opzioni di informazioni sul profilo SIP come illustrato. 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrizione  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Nello stesso schermo scorrere verso il basso fino alla sezione informazioni sul profilo SDP. Il **modificatore della larghezza di banda a livello di sessione SDP per l'opzione Early offer e reinvitates** è impostato per impostazione predefinita su Tias e As. Modificare questa opzione solo per TIAS. Se si lascia questa opzione all'impostazione predefinita, Skype for Business Server non capirà le informazioni sul modificatore della larghezza di banda nel messaggio SIP. TIAS indica un'applicazione indipendente per il trasporto, mentre il metodo specifica l'applicazione. Queste sono le opzioni SIP specificate in RFC3890.
    
10. Nello stesso schermo scorrere verso il basso. Nella configurazione specifica del trunk del profilo SIP, selezionare **Early offer support for Voice and video calls** e impostarlo sull'opzione **obbligatorio (inserire MTP se necessario)** . Ciò consentirà a un CUCM di configurare una chiamata SIP in uscita con offerta anticipata. Una nuova funzionalità di un CUCM 8,5 e oltre è che supporta l'installazione delle chiamate in uscita con l'offerta iniziale senza richiedere il punto di terminazione multimediale (MTP).
    
11. Verificare che nella sezione ping opzioni SIP sia selezionata la casella accanto a "attiva opzioni ping per monitorare lo stato di destinazione dei trunk con il tipo di servizio ' None (impostazione predefinita)'".
    
12. Al termine, fare clic su **Aggiungi nuovo**.
    
13. Passare a Cisco Unified CM Administration- \> Device- \> trunk. 
    
14. Impostare il protocollo del dispositivo su SIP e premere **Avanti**.
    
15. In informazioni sul dispositivo, impostare il nome e la descrizione del dispositivo (probabilmente su un valore analogo a SfBVideoInterop_SIPTrunk) e impostare l'elenco dei gruppi di risorse multimediali su un MRGL che contiene le risorse multimediali corrette. 
    
16. Scorrere verso il basso ulteriormente. Il punto di terminazione multimediale (MTP) non è necessario per le chiamate video, se non è già stato deselezionato, deselezionare la casella di controllo. Selezionare l'opzione per l' **esecuzione in tutti i nodi di cm unificati attivi**. Tenere presente che è necessario aggiungere tutti i nodi di un CUCM alla configurazione di Skype for Business Server.
    
17. Scorrere verso il basso ulteriormente. Impostare le chiamate in ingresso e le opzioni relative alle impostazioni delle parti collegate come illustrato.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Chiamata dello spazio di ricerca  <br/> |CSS_SfBVideoInterop  <br/> |
    |Spazio di ricerca chiamata AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS di trasformazione delle parti connesse  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scorrere verso il basso ulteriormente. Nella sezione destinazione informazioni SIP della configurazione del trunk SIP specificare il nome di dominio completo del pool VIS o l'indirizzo IP dei singoli server VIS nel pool (aggiunta di più voci). Nella porta di destinazione specificare la porta che VIS è in ascolto per le connessioni da un CUCM (il valore predefinito è 6001). Specificare anche il profilo di sicurezza trunk SIP e il profilo SIP creato in precedenza, come illustrato.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Profilo di sicurezza trunk SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Reinstradamento dello spazio di ricerca delle chiamate  <br/> |CSS_SfBVideoInterop  <br/> |
    |Finestra di dialogo riferisci chiamata dello spazio di ricerca  <br/> |CSS_SfBVideoInterop  <br/> |
    |Sottoscrizione dello spazio di ricerca di chiamata  <br/> |CSS_SfBVideoInterop  <br/> |
    |Profilo SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Metodo di segnalazione DTMF  <br/> |RFC 2833  <br/> |
   
19.  Scorrere verso il basso ulteriormente. Impostare le informazioni di registrazione come appropriate per il sistema. È bene lasciarla impostata su **None**. 
    
20. Al termine, fare clic su **Aggiungi nuovo**.
    
21. Accedere a Cisco Unified CM Administration- \> call routing- \> Route/Hunt- \> Route pattern.
    
22. Nella schermata Configurazione modello di route immettere i parametri di definizione del modello riportati di seguito. Scorrere verso il basso fino alla sezione chiamata trasformazioni party e impostare la maschera come illustrato, quindi fare clic su **Aggiungi nuovo** al termine.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Motivo percorso  <br/> |7779999  <br/> |
    |Partizione di route  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrizione  <br/> |Partizione per SfBVideoInterop  <br/> |
    |Gateway/elenco di route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Mask Transform denominato Party  <br/> |+ 14257779999  <br/> |
   
23. Passare a Cisco Unified CM Administration- \> call routing- \> SIP Route pattern.
    
24. Nella schermata Configurazione modello di route SIP impostare le opzioni di definizione dei modelli come illustrato e fare clic su **Aggiungi nuovo**.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    | Utilizzo del modello <br/> |Routing del dominio  <br/> |
    |Modello IPv4  <br/> |contoso.com (lasciare vuoto se si utilizza IPv6)  <br/> |
    |Modello IPv6  <br/> |contoso.com (lasciare vuoto se si utilizza IPv4)  <br/> |
    |Descrizione  <br/> |SIPRoute pattern to mediarv  <br/> |
    |Partizione di route  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Trunk SIP/elenco di route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Casella di controllo modello di blocco  <br/> |lascia deselezionato  <br/> |
   
25. Se sono state modificate le velocità dei bit audio o video dalle impostazioni predefinite, sarà necessario restituirle ai valori predefiniti. Per impostare la velocità in bit per le chiamate audio/video, accedere a Cisco Unified CM Administration- \> System- \> Region Information- \> Region. Di seguito sono riportati i valori predefiniti per riferimento:
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Area geografica  <br/> |Predefiniti  <br/> |
    |Elenco delle preferenze dei codec audio  <br/> |Impostazione predefinita del sistema  <br/> |
    |Velocità massima in bit audio  <br/> |64 Kbps (G. 722, G. 711)  <br/> |
    |Velocità in bit massima sessione per le chiamate video  <br/> |200000 Kbps  <br/> |
    |Velocità in bit massima sessione  <br/> |2 miliardi Kbps  <br/> |
   
A questo punto il gateway video di un CUCM è configurato per funzionare con il VIS. Sarà necessario eseguire la configurazione corrispondente su ogni videoconferenza che si desidera integrare.
> [!NOTE]
> Per migliorare la resilienza, è possibile configurare il gateway di un CUCM in modo che funzioni con un secondo video Interop server o un pool VIS. Per ulteriori informazioni, vedere [meccanismi di resilienza](../../plan-your-deployment/video-interop-server.md#resiliency) .
  
## <a name="see-also"></a>Vedere anche

[Configurare un videoconferenza per l'interoperabilità con Skype for Business Server](configure-a-vtc-for-interoperation.md)
