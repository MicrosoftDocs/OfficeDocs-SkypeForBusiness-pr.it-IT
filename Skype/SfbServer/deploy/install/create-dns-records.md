---
title: Creare record DNS per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: "Riepilogo: informazioni su come configurare DNS e creare record DNS per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: f5f5c40805388d6a1c861a53bae0a85c27537056
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245004"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Creare record DNS per Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare DNS e creare record DNS per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.
  
Affinché Skype for Business Server funzioni correttamente, è necessario che sia presente un certo numero di impostazioni DNS (Domain Name System). In modo che i client sappiano come accedere ai servizi e che i server sappiano reciprocamente. Queste impostazioni devono essere completate solo una volta per ogni distribuzione, perché una volta assegnata una voce DNS è disponibile in tutto il dominio. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. La creazione di record DNS include il passaggio 5 di 8. Per altre informazioni sulla pianificazione del DNS, vedere [requisiti ambientali per i requisiti di Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o server [per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> È importante notare che questo è solo un esempio di come creare record DNS in un ambiente DNS di Windows Server. Ci sono molte altre voci DNS necessarie per Skype for Business Server e la procedura per la creazione di record DNS dipende dal sistema in uso per gestire il DNS nell'organizzazione. Per un elenco completo dei requisiti per il DNS, vedere [requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Diagramma di panoramica](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurare il DNS

I record DNS sono necessari affinché Skype for Business Server funzioni correttamente e sia accessibile dagli utenti.
  
Questo esempio usa un FQDN con bilanciamento del carico DNS denominato pool. contoso. local. Questo pool è costituito da tre server con Skype for Business Server Enterprise Edition. Un server front-end Standard Edition può contenere solo un singolo server. Usando Standard Edition, si utilizzerebbe solo il nome di dominio completo (FQDN) del server Single Standard Edition quando si fa riferimento al ruolo front-end invece di creare un pool di server con bilanciamento del carico DNS, come illustrato in questo esempio. Questo semplice esempio che usa solo il ruolo front-end include le voci DNS nella tabella seguente. Per pianificare i requisiti DNS specifici, vedere [requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Descrizione**|**Tipo di record**|**Nome**|**Risolve in**|**Tipo di bilanciamento del carico**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN dei servizi Web interni  <br/> |A  <br/> |webint. contoso. local  <br/> |VIP per servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|FQDN del pool  <br/> |A  <br/> |pool. contoso. local  <br/> |Indirizzo IP del server SFB01  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01. contoso. local  <br/> |Indirizzo IP del server SFB01  <br/> |DNS  <br/> |
|FQDN del pool  <br/> |A  <br/> |pool. contoso. local  <br/> |Indirizzo IP del server SFB02  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02. contoso. local  <br/> |Indirizzo IP del server SFB02  <br/> |DNS  <br/> |
|FQDN del pool  <br/> |A  <br/> |pool. contoso. local  <br/> |Indirizzo IP del server SFB03  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03. contoso. local  <br/> |Indirizzo IP del server SFB03  <br/> |DNS  <br/> |
|Individuazione automatica di Skype for business  <br/> |A  <br/> |LyncdiscoverInternal. contoso. local  <br/> |VIP per servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice della riunione  <br/> |A  <br/> |Meet. contoso. local  <br/> |VIP per servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice con accesso esterno  <br/> |A  <br/> |dialin. contoso. local  <br/> |VIP per servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice dell'utilità di pianificazione Web  <br/> |A  <br/> |Scheduler. contoso. local  <br/> |VIP per servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice di amministrazione  <br/> |A  <br/> |admin. contoso. local  <br/> |VIP per servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|Individuazione legacy  <br/> |SRV  <br/> |_sipinternaltls. _tcp. contoso. local  <br/> |FQDN del pool (porta 5061)  <br/> |N/D  <br/> |
   
### <a name="create-dns-records"></a>Creare record DNS

1. Accedere al server DNS e aprire **Server Manager**.
    
2. Fare clic sul menu a discesa **strumenti** e quindi su **DNS**.
    
3. Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi espandere il dominio SIP in cui verrà installato Skype for Business Server.
    
4. Fare clic con il pulsante destro del mouse sul dominio SIP e scegliere **nuovo host (a o AAAA)**, come illustrato nella figura.
    
     ![selezione di un nuovo record](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Nella casella **nome** Digitare il nome del record host (il nome del dominio verrà accodato automaticamente).
    
6. Nella **casella indirizzo IP**Digitare l'indirizzo IP del server front-end individuale e quindi selezionare **Crea record puntatore associato (PTR)** o **consentire a qualsiasi utente autenticato di aggiornare i record DNS con lo stesso nome proprietario**, se applicabile. Tieni presente che questo presuppone che il DNS venga usato per il bilanciamento del carico del traffico con l'eccezione dei servizi Web. In questo esempio abbiamo tre server front-end come illustrato nella tabella.
    
   |**Nome server**|**Tipo**|**Dati**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Crea quindi le voci di bilanciamento del carico DNS per il pool. Il bilanciamento del carico DNS consente al DNS di inviare richieste ai singoli server del pool mentre usa lo stesso nome del pool DNS. Per altre informazioni sul DNS e sul bilanciamento del carico, vedere [requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > Il raggruppamento di più server insieme è disponibile solo nelle distribuzioni di Enterprise Edition. Se si distribuisce un singolo server aziendale o un server Standard Edition, è necessario creare solo un record per il server singolo. 
  
    Ad esempio, se si ha un pool denominato pool. contoso. local e tre server front-end, è necessario creare le voci DNS seguenti:
    
   |**FQDN**|**Tipo**|**Dati**|
   |:-----|:-----|:-----|
   |pool. contoso. local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool. contoso. local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool. contoso. local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Continuare a creare record per tutti i server della distribuzione pianificata. 
    
9. Per creare il record servizio (SRV) per l'individuazione legacy, fare clic con il pulsante destro del mouse sul dominio SIP e selezionare **altri nuovi record**.
    
10. In **selezionare un tipo di record delle risorse**fare clic su **posizione servizio (SRV)** e quindi su **Crea record**.
    
11. Fare clic su **servizio**e quindi digitare **_sipinternaltls**.
    
12. Fare clic su **protocollo**e quindi digitare **_tcp**.
    
13. Fare clic su **numero di porta**e quindi digitare **5061**.
    
14. Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo del pool o del server Standard Edition.
    
     ![Screenshot della finestra di dialogo nuovo record di risorse.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Fare clic su **OK**e quindi su **fine**.
    
### <a name="verify-dns-records"></a>Verificare i record DNS

1. Accedere a un computer client nel dominio con un account membro del gruppo Authenticated Users o con autorizzazioni equivalenti.
    
2. Fare clic sul pulsante **Start**e quindi digitare **cmd**e premere INVIO.
    
3. Digitare **nslookup \<FQDN del pool\> front-end** o ** \<del nome FQDN del server Standard Edition o single Enterprise Edition\>**, quindi premere INVIO.
    
4. Continuare a verificare il resto dei record A per la distribuzione.
    
5. Se si supportano client legacy e si crea il record SRV, verificarlo digitando **set type = srv** al prompt di **nslookup** e quindi premere INVIO.
    
6. Digitare **_sipinternaltls. _tcp. *dominio* ** (ad esempio, _sipinternaltls. _tcp. contoso. local) e quindi premere INVIO.
    
7. L'output previsto dovrebbe essere simile a quello mostrato nella figura. Tieni presente che non tutti i record DNS vengono visualizzati nell'output di esempio, ma tutti i record devono essere verificati. 
    
     ![Verificare le impostazioni DNS.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

