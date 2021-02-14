---
title: Creare record DNS per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: "Riepilogo: informazioni su come configurare DNS e creare record DNS per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo:  https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 3808216e0732d6e3af2f32e27d79d78727ddc105
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812136"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Creare record DNS per Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare DNS e creare record DNS per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Per il corretto funzionamento di Skype for Business Server, è necessario che siano presenti diverse impostazioni DNS (Domain Name System). In questo modo i client sanno come accedere ai servizi e che i server si conoscono reciprocmente. Queste impostazioni devono essere completate una sola volta per ogni distribuzione perché una volta assegnata una voce DNS è disponibile in tutto il dominio. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. La creazione di record DNS comprende il passaggio 5 di 8. Per ulteriori informazioni sulla pianificazione del DNS, vedere Requisiti ambientali per i requisiti di [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Server per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
> [!IMPORTANT]
> È importante notare che questo è solo un esempio di come creare record DNS in un ambiente DNS di Windows Server. Esistono molte altre voci DNS necessarie per Skype for Business Server e la procedura per la creazione dei record DNS dipende dal sistema utilizzato per gestire DNS nell'organizzazione. Per un elenco completo dei requisiti per DNS, vedere [Requisiti DNS per Skype for Business Server.](../../plan-your-deployment/network-requirements/dns.md) 
  
![Diagramma di panoramica](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurazione del DNS

I record DNS sono necessari per il corretto funzionamento di Skype for Business Server e l'accessibilità da parte degli utenti.
  
In questo esempio viene utilizzato un FQDN con bilanciamento del carico DNS denominato pool.contoso.local. Questo pool è costituito da tre server che eseguono Skype for Business Server Enterprise Edition. Un server front-end Standard Edition può contenere un solo server. Utilizzando Standard Edition, è possibile utilizzare solo il nome di dominio completo (FQDN) del singolo server Standard Edition quando si fa riferimento al ruolo front-end anziché creare un pool di server con bilanciamento del carico DNS, come illustrato in questo esempio. In questo semplice esempio che utilizza solo il ruolo front-end sono incluse le voci DNS nella tabella seguente. Per pianificare i requisiti DNS specifici, vedere [Requisiti DNS per Skype for Business Server.](../../plan-your-deployment/network-requirements/dns.md) 
  
 
|**Descrizione**|**Tipo di record**|**Nome**|**Viene risolto in**|**Tipo di bilanciamento del carico**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN servizi Web interni  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP per i servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|FQDN pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Indirizzo IP del server SFB01  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Indirizzo IP del server SFB01  <br/> |DNS  <br/> |
|FQDN pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Indirizzo IP del server SFB02  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Indirizzo IP del server SFB02  <br/> |DNS  <br/> |
|FQDN pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Indirizzo IP del server SFB03  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Indirizzo IP del server SFB03  <br/> |DNS  <br/> |
|Individuazione automatica di Skype for Business  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP per i servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice riunione  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP per i servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice per l'accesso esterno  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP per i servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice dell'Utilità di pianificazione Web  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP per i servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|URL semplice di amministrazione  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP per i servizi Web interni  <br/> |Software e hardware supportati  <br/> |
|Individuazione legacy  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN pool (porta 5061)  <br/> |N/D  <br/> |
   
### <a name="create-dns-records"></a>Creare record DNS

1. Accedere al server DNS e aprire **Server Manager.**
    
2. Fare clic sul menu **a** discesa Strumenti e quindi su **DNS.**
    
3. Nell'albero della console per il dominio SIP espandere **Zone** di ricerca diretta e quindi espandere il dominio SIP in cui verrà installato Skype for Business Server.
    
4. Fare clic con il pulsante destro del mouse sul dominio SIP e selezionare Nuovo host (A o **AAAA),** come illustrato nella figura.
    
     ![selezione di un nuovo record A](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Nella casella **Nome** digitare il nome del record host (il nome di dominio verrà aggiunto automaticamente).
    
6. Nella casella **Indirizzo IP** digitare l'indirizzo IP del singolo server front-end e quindi selezionare Crea record puntatore **(PTR)** associato o Consenti a qualsiasi utente autenticato di aggiornare i record **DNS** con lo stesso nome proprietario, se applicabile. Si noti che si presuppone che il DNS sia utilizzato per bilanciare il carico di tutto il traffico ad eccezione dei servizi Web. In questo esempio sono presenti tre server front-end, come illustrato nella tabella.
    
   |**Nome server**|**Tipo**|**Dati**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Successivamente, creare le voci di bilanciamento del carico DNS per il pool. Il bilanciamento del carico DNS consente a DNS di inviare richieste ai singoli server del pool utilizzando lo stesso nome del pool DNS. Per ulteriori informazioni su DNS e bilanciamento del carico, vedere [Requisiti DNS per Skype for Business Server.](../../plan-your-deployment/network-requirements/dns.md) 
    
    > [!NOTE]
    > Il pool di più server è disponibile solo nelle distribuzioni Enterprise Edition. Se si distribuisce un singolo server Enterprise o Standard Edition, è necessario creare solo un record A per il singolo server. 
  
    Ad esempio, se si ha un pool denominato pool.contoso.local e tre server front-end, è necessario creare le voci DNS seguenti:
    
   |**FQDN**|**Tipo**|**Dati**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Continuare a creare record A per tutti i server della distribuzione pianificata. 
    
9. Per creare il record del servizio (SRV) per l'individuazione legacy, fare clic con il pulsante destro del mouse sul dominio SIP e scegliere **Altri nuovi record.**
    
10. In **Selezionare tipo di record di risorsa** fare clic su **Posizione servizio (SRV)** e quindi su **Crea record**.
    
11. Fare clic su **Servizio** e quindi digitare **_sipinternaltls**.
    
12. Fare clic su **Protocollo** e quindi digitare **_tcp**.
    
13. Fare clic su **Numero porta** e quindi digitare **5061**.
    
14. Fare **clic su Host che offre questo** servizio e quindi digitare il nome di dominio completo del pool o del server Standard Edition.
    
     ![Screenshot della finestra di dialogo del nuovo record di risorse.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Fare clic su **OK** e quindi su **Fine**.
    
### <a name="verify-dns-records"></a>Verificare i record DNS

1. Accedere a un computer client nel dominio con un account membro del gruppo Authenticated Users o con autorizzazioni equivalenti.
    
2. Fare **clic sul** pulsante Start e quindi digitare **cmd** e premere INVIO.
    
3. Digitare **nslookup \<FQDN of the Front End pool\>** o e premere **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** INVIO.
    
4. Continuare a verificare gli altri record A per la distribuzione.
    
5. Se si supportano client legacy e si crea il record SRV, verificarlo digitando **set type=srv** al prompt **nslookup** e quindi premere INVIO.
    
6. Digitare **_sipinternaltls._tcp. *domain*** (ad esempio, _sipinternaltls._tcp.contoso.local), quindi premere INVIO.
    
7. L'output previsto deve essere simile a quello mostrato nella figura. Si noti che non tutti i record DNS vengono visualizzati nell'output di esempio, ma tutti i record devono essere verificati. 
    
     ![Verificare le impostazioni dns.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

