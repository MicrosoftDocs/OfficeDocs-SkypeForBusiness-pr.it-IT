---
title: Creare un pool VIS in Skype for Business Server
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
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Riepilogo: creare un pool di Video Interop Server in Skype for Business Server utilizzando Generatore di topologie.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802056"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Creare un pool VIS in Skype for Business Server
 
**Riepilogo:** Creare un pool di Video Interop Server in Skype for Business Server usando Generatore di topologie.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Creare un pool VIS o VIS tramite Generatore di topologie

1. Aprire Generatore di topologie nel server front-end. Nel riquadro sinistro di Generatore di topologie fare clic con il pulsante destro del mouse su **Pool di Video Interop Server** e scegliere Nuovo pool di Video Interop **Server.** 
    
2. Verrà aperta la procedura **guidata Crea un nuovo pool di Video Interop Server.** Specificare l'FQDN del pool per il nuovo Video Interop Server e selezionare Il pool ha un **solo server** o questo **pool** ha più server in base alle proprie esigenze, quindi premere **Avanti.**
    
    Se si desidera distribuire un pool Video Interop Server per garantire la disponibilità elevata, selezionare **Questo pool dispone di più server.** Tieni presente questa opzione che: 
    
    - È necessario distribuire il bilanciamento del carico DNS per supportare i pool di Video Interop Server. 
    
   - Nella pagina successiva, per l'elemento Definire i computer nel **pool,** immettere **l'FQDN** computer di ogni server del pool nel campo di testo e quindi fare clic su **Aggiungi.** Ripetere questo passaggio per aggiungere un altro Video Interop Server al pool. Dopo aver definito tutti i computer nel pool, premere **Avanti.**
    
     Se si desidera distribuire un solo Video Interop Server nel pool perché non è necessaria la disponibilità elevata, selezionare Il pool dispone di un **solo server** e premere **Avanti.**
    
3. Selezionare il pool/FE hop successivo nell'elenco a discesa e premere **Avanti.**
    
4. Selezionare un pool di server perimetrali da associare al VIS e premere **Fine.**
    
5. Impostare una porta TCP o TLS.
    
    Selezionare il video Interop Server appena aggiunto nel riquadro sinistro di Generatore di topologie, fare clic con il pulsante destro del mouse su di esso e scegliere **Modifica proprietà.** Abilitare o aggiornare la porta TCP o TLS in base ai requisiti e scegliere **OK.** Anche se per impostazione predefinita VIENE aggiunto TLS, solo TCP è stato completamente testato con Cisco Unified Communications Manager (CallManager o CUCM).
    
6. Aggiungere un gateway video. A tale scopo, espandere Componenti condivisi, fare clic con il pulsante destro del mouse su **Gateway video** e selezionare Nuovo **gateway video.**
    
7. Fornire l'FQDN o l'indirizzo IP del gateway video. Il gateway video potrebbe essere in un sottodominio o in un dominio diverso. Il modello CUCM utilizzato dai VTC del sistema funge da gateway video.
    
8. Selezionare IPv4 o IPv6 in base alle esigenze. È possibile utilizzare tutti gli indirizzi IP configurati o limitare l'utilizzo del servizio agli indirizzi IP selezionati.
    
9. Selezionare la porta di attesa del gateway video. Selezionare il protocollo di trasporto (TCP o TLS) e associarlo a un Video Interop Server configurato per un trunk SIP video. Il protocollo di trasporto per il gateway video deve corrispondere al protocollo di trasporto configurato per il VIS.
    
10. Al termine del passaggio precedente viene aggiunto un trunk VIDEO SIP corrispondente. Fare clic con il pulsante destro del mouse sul trunk video SIP e selezionare il trunk appena aggiunto. Il nome del trunk SIP video, il server di interoperabilità video associato, il protocollo di trasporto SIP e la porta possono essere tutti modificati. 
    
    > [!NOTE]
    >  Un Video Interop Server supporta trunk 1:N. Di conseguenza, è possibile aggiungere più trunk, associati a un singolo Video Interop Server, in cui ogni trunk termina in un gateway video diverso. Il limite è che un determinato gateway video dispone di un solo trunk che può essere definito per la distribuzione di Skype for Business Server.
  
11. Pubblicare il documento della topologia come descritto in Creare e pubblicare una nuova topologia [in Skype for Business Server 2015.](../../deploy/install/create-and-publish-new-topology.md)
    
    > [!NOTE]
    > Per migliorare la resilienza, è possibile configurare un secondo pool Video Interop Server o VIS oppure un pool Front End di backup. Per [ulteriori informazioni, vedere Meccanismi](../../plan-your-deployment/video-interop-server.md#resiliency) di resilienza.
  
Tutte le attività eseguite utilizzando Generatore di topologie dovrebbero ora essere completate. Procedere con l'installazione del software nel nuovo server o server VIS.
## <a name="see-also"></a>Vedere anche

[Distribuire il ruolo del server VIS in Skype for Business Server](deploy-the-vis-server-role.md)

[Pianificare Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md)
