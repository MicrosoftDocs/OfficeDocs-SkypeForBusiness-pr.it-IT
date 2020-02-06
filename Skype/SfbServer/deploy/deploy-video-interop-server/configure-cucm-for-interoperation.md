---
title: Configurare CUCM per l'interoperabilità con Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: "Riepilogo: configurare CUCM per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 0f8b5321b482d78d9dc833471323ae842c247246
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798073"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>Configurare CUCM per l'interoperabilità con Skype for Business Server
 
**Riepilogo:** Configura CUCM per l'utilizzo con Skype for Business Server.
  
> [!CAUTION]
> Questa funzionalità viene testata con Cisco Unified Communications Manager (CallManager o CUCM) versione 10,5 usando Trunks setup su TCP only. Verificare che l'ambiente CUCM soddisfi questi criteri prima di procedere. 
  
Le impostazioni descritte in questo articolo sono intese solo come esempi di come CUCM può essere configurato per l'utilizzo con un VIS. Altre impostazioni e/o usi della funzionalità CUCM alternativa possono essere usati anche per ottenere lo stesso risultato. Nessuna raccomandazione è implicita sulla configurazione ottimale per uno scenario specifico.
  
Per l'interoperabilità con il VIS è necessario confermare o modificare alcune impostazioni di CUCM. Seguire le procedure descritte di seguito per evitare di perdere le impostazioni richieste.
  
### <a name="configure-the-cucm"></a>Configurare il CUCM

1. Accedere a CUCM e passare a Cisco Unified CM Administration-\>call routing-\>classe di controllo-\>partizione.
    
2. Nella schermata di configurazione della partizione immettere il nome e la descrizione della partizione e fare clic su **Aggiungi nuovo**.
    
3. Passare a Cisco Unified CM Administration-\>call routing-\>classe di spazio di ricerca\>per la chiamata di controllo.
    
4. Nella schermata di configurazione dello spazio di ricerca chiamante immettere il nome per lo spazio di ricerca chiamante e, in partizioni selezionate, immettere il nome della partizione appena creata. Fare clic su **Salva** al termine.
    
5. Passare a Cisco Unified CM Administration-\>System-\>Security-profilo\>di sicurezza trunk SIP.
    
6. Nella schermata di configurazione del profilo di sicurezza trunk SIP impostare le opzioni di informazioni del profilo di sicurezza trunk SIP come illustrato, quindi fare clic su **Aggiungi nuovo**.
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |Modalità di sicurezza del dispositivo  <br/> |Non sicuro  <br/> |
   |Tipo di trasporto in arrivo  <br/> |TCP + UDP  <br/> |
   |Tipo di trasporto in uscita  <br/> |TCP  <br/> |
   |Porta in arrivo  <br/> |5060  <br/> |
   
7. Passare a Cisco Unified CM Administration-\>\>impostazioni dispositivo-dispositivo-\>profilo SIP.
    
8. Nella schermata di configurazione del profilo SIP impostare le opzioni di informazioni del profilo SIP come illustrato. 
    
   |**Parametro**|**Impostazione consigliata**|
   |:-----|:-----|
   |Nome  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |Descrizione  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. Nella stessa schermata scorrere verso il basso fino alla sezione informazioni sul profilo SDP. Il **modificatore della larghezza di banda a livello di sessione SDP per l'opzione offerta anticipata e ri-invita** è impostato per impostazione predefinita su Tias e così via. Modificare questa opzione solo in TIAS. Se si omette questa opzione per impostazione predefinita, Skype for Business Server non comprenderà le informazioni sul modificatore della larghezza di banda nel messaggio SIP. TIAS indica un'applicazione indipendente per il trasporto, mentre specifica l'applicazione. Queste sono le opzioni SIP specificate in RFC3890.
    
10. Nella stessa schermata scorrere verso il basso ulteriormente. Sotto la configurazione specifica del trunk del profilo SIP selezionare **supporto preventivo per le chiamate vocali e videochiamate** e impostarlo sull'opzione **obbligatorio (inserire MTP se necessario)** . Ciò consentirà a CUCM di configurare una chiamata SIP in uscita con offerta anticipata. Una nuova funzionalità in CUCM 8,5 e oltre è che supporta la configurazione delle chiamate in uscita con offerta anticipata senza richiedere il punto di terminazione multimediale (MTP).
    
11. Verificare che nella sezione ping opzioni SIP la casella sia selezionata accanto a "attiva opzioni ping per monitorare lo stato di destinazione per i trunk con il tipo di servizio" Nessuna (impostazione predefinita) "."
    
12. Al termine, fare clic su **Aggiungi nuovo**.
    
13. Passare a Cisco Unified CM Administration-\>Device-\>trunk. 
    
14. Impostare il protocollo del dispositivo su SIP e premere **Avanti**.
    
15. In informazioni sul dispositivo impostare il nome e la descrizione del dispositivo (probabilmente in modo simile a SfBVideoInterop_SIPTrunk) e impostare l'elenco di gruppi di risorse multimediali su un MRGL che contiene le risorse multimediali appropriate. 
    
16. Scorrere verso il basso ulteriormente. Il punto di terminazione multimediale (MTP) non è necessario per le videochiamate, se non è già deselezionato, deselezionarlo. Selezionare l'opzione per l' **esecuzione in tutti i nodi di cm unificati attivi**. Tieni presente che devi aggiungere tutti i nodi CUCM alla configurazione di Skype for Business Server.
    
17. Scorrere verso il basso ulteriormente. Impostare le opzioni per le chiamate in ingresso e le impostazioni delle entità connesse come illustrato.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Chiamata dello spazio di ricerca  <br/> |CSS_SfBVideoInterop  <br/> |
    |Spazio di ricerca chiamate AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |CSS di trasformazione delle entità connesse  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. Scorrere verso il basso ulteriormente. Nella sezione destinazione informazioni SIP della configurazione trunk SIP specificare il nome di dominio completo del pool VIS o l'indirizzo IP dei singoli server VIS nel pool (aggiunta di più voci). Nella porta di destinazione specificare la porta che VIS sta ascoltando per le connessioni da CUCM (il valore predefinito è 6001). Specifica anche il profilo di sicurezza trunk SIP e il profilo SIP creato in precedenza, come illustrato.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Profilo di sicurezza trunk SIP  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |Rirouting dello spazio di ricerca delle chiamate  <br/> |CSS_SfBVideoInterop  <br/> |
    |Finestra di dialogo riferisci chiamata dello spazio di ricerca  <br/> |CSS_SfBVideoInterop  <br/> |
    |Iscriversi chiamando lo spazio di ricerca  <br/> |CSS_SfBVideoInterop  <br/> |
    |Profilo SIP  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |Metodo di segnalazione DTMF  <br/> |RFC 2833  <br/> |
   
19.  Scorrere verso il basso ulteriormente. Impostare le informazioni di registrazione appropriate per il sistema. È bene lasciarlo impostato su **None**. 
    
20. Al termine, fare clic su **Aggiungi nuovo**.
    
21. Passare a Cisco Unified CM Administration-routing\>delle chiamate-\>Route/Hunt-\>pattern route.
    
22. Nella schermata di configurazione del modello di route Immetti i parametri di definizione del pattern mostrati di seguito. Scorrere verso il basso fino alla sezione trasformazioni delle entità chiamate e impostare la maschera come illustrato, quindi fare clic su **Aggiungi nuovo** al termine.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Modello di route  <br/> |7779999  <br/> |
    |Partizione di route  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Descrizione  <br/> |Partizione per SfBVideoInterop  <br/> |
    |Elenco gateway/Route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Maschera di trasformazione partito chiamata  <br/> |+ 14257779999  <br/> |
   
23. Passare a Cisco Unified CM Administration-\>routing delle chiamate-\>modello di route SIP.
    
24. Nella schermata di configurazione del modello di route SIP impostare le opzioni di definizione del pattern come illustrato, quindi fare clic su **Aggiungi nuovo**.
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    | Uso di pattern <br/> |Routing del dominio  <br/> |
    |Modello IPv4  <br/> |contoso.com (lasciando vuoto se si usa IPv6)  <br/> |
    |Modello IPv6  <br/> |contoso.com (lasciando vuoto se si usa IPv4)  <br/> |
    |Descrizione  <br/> |Modello SIPRoute in mediarv  <br/> |
    |Partizione di route  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |Trunk SIP/elenco di route  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Casella di controllo modello di blocco  <br/> |Lascia deselezionata  <br/> |
   
25. Se sono state modificate le velocità in bit audio o video dalle impostazioni predefinite, sarà necessario restituirle ai valori predefiniti. Per impostare la velocità in bit per le chiamate audio/video, passare a Cisco Unified CM Administration\>-System\>-Region Information\>-Region. Le impostazioni predefinite sono illustrate di seguito per riferimento:
    
    |**Parametro**|**Impostazione consigliata**|
    |:-----|:-----|
    |Area  <br/> |Predefinita  <br/> |
    |Elenco preferenze codec audio  <br/> |Impostazione predefinita del sistema  <br/> |
    |Velocità in bit audio massima  <br/> |64 Kbps (G. 722, G. 711)  <br/> |
    |Velocità in bit massima della sessione per le videochiamate  <br/> |200000 Kbps  <br/> |
    |Velocità in bit massima della sessione  <br/> |2 miliardi Kbps  <br/> |
   
A questo punto il gateway video di CUCM è configurato per l'utilizzo con il VIS. La configurazione corrispondente deve essere eseguita su ogni VTC che si vuole integrare.
> [!NOTE]
> Per migliorare la resilienza, è consigliabile configurare il gateway di CUCM per l'utilizzo con un secondo video Interop server o il pool VIS. Per altre informazioni, Vedi [meccanismi di resilienza](../../plan-your-deployment/video-interop-server.md#resiliency) .
  
## <a name="see-also"></a>Vedere anche

[Configurare un VTC per l'interoperabilità con Skype for Business Server](configure-a-vtc-for-interoperation.md)
