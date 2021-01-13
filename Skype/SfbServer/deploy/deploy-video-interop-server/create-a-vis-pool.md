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
description: 'Riepilogo: creare un pool di interoperabilità video in Skype for Business Server utilizzando Generatore di topologie.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802056"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Creare un pool VIS in Skype for Business Server
 
**Riepilogo:** Creare un pool di video Interop server in Skype for Business Server tramite Generatore di topologie.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Creare un pool VIS o VIS tramite Generatore di topologie

1. Aprire Generatore di topologie nel front end server. Nel riquadro sinistro di generatore di topologie fare clic con il pulsante destro del mouse su **pool video Interop server** e scegliere **nuovo pool di interoperabilità video**. 
    
2. Verrà visualizzata la procedura guidata **Crea un nuovo pool di interoperabilità di video** . Specificare il nome di dominio completo del pool per il nuovo server di interoperabilità video e selezionare **questo pool ha un solo server** o **questo pool dispone di più server** in base al requisito, quindi premere **Avanti**.
    
    Se si desidera distribuire un pool di interoperabilità video per fornire disponibilità elevata, selezionare **questo pool dispone di più server**. Tenere presente questa opzione: 
    
    - È necessario distribuire il bilanciamento del carico DNS per supportare i pool di server di interoperabilità video. 
    
   - Nella pagina successiva, per l'elemento **define the computers in this pool** , immettere il **nome di dominio completo del computer** di ogni server nel pool nel campo di testo e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per aggiungere un altro server di interoperabilità video al pool. Dopo aver definito tutti i computer nel pool, premere **Avanti**.
    
     Se si desidera distribuire un solo server di interoperabilità video nel pool perché non è necessaria una disponibilità elevata, selezionare **questo pool con un solo server** e premere **Avanti**.
    
3. Selezionare il pool hop successivo/FE nell'elenco a discesa e premere **Avanti**.
    
4. Selezionare un pool di server perimetrali da associare al VIS e premere **fine**.
    
5. Impostare una porta TCP o TLS.
    
    Selezionare il server di interoperabilità video appena aggiunto dal riquadro sinistro del generatore di topologie, fare clic con il pulsante destro del mouse e scegliere **modifica proprietà**. Abilitare o aggiornare la porta TCP o TLS per ogni requisito e scegliere **OK**. Anche se per impostazione predefinita è stato aggiunto TLS, solo TCP è stato completamente testato con Cisco Unified Communications Manager (CallManager o un CUCM).
    
6. Aggiungere un gateway video. A tale scopo, espandere componenti condivisi, fare clic con il pulsante destro del mouse su **gateway video** e scegliere **nuovo gateway video**.
    
7. Specificare il nome di dominio completo o l'indirizzo IP del gateway video. Il gateway video può trovarsi in un sottodominio o in un altro dominio. Il un CUCM utilizzato dall'VTCs del sistema funge da gateway video.
    
8. Selezionare IPv4 o IPv6 in base alle esigenze. È possibile utilizzare tutti gli indirizzi IP configurati o limitare l'utilizzo del servizio a indirizzi IP selezionati.
    
9. Selezionare la porta di attesa del gateway video. Selezionare il protocollo di trasporto (TCP o TLS) e associarlo a un server di interoperabilità video configurato per un trunk SIP video. Il protocollo di trasporto per il gateway video deve corrispondere al protocollo di trasporto configurato per il VIS.
    
10. Dopo aver completato il passaggio precedente, viene aggiunto un trunk video SIP corrispondente. Fare clic con il pulsante destro del mouse sul trunk video SIP e selezionare il trunk appena aggiunto. È possibile modificare il nome del trunk SIP video, il server di interoperabilità video associato, il protocollo di trasporto SIP e la porta. 
    
    > [!NOTE]
    >  Un server di interoperabilità video supporta trunk 1: N. È quindi possibile aggiungere più trunk, che sono associati a un singolo server di interoperabilità video, in cui ogni trunk termina su un gateway video diverso. La limitazione è che un particolare gateway video ha un solo trunk che può essere definito nella distribuzione di Skype for Business Server.
  
11. Pubblicare il documento della topologia come descritto in [creare e pubblicare una nuova topologia in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Per migliorare la resilienza, è possibile configurare un secondo video Interop server o un pool VIS o un pool Front End di backup. Per ulteriori informazioni, vedere [meccanismi di resilienza](../../plan-your-deployment/video-interop-server.md#resiliency) .
  
Tutte le attività eseguite con generatore di topologie devono essere completate. Procedere con l'installazione del software nel nuovo server o server VIS.
## <a name="see-also"></a>Vedere anche

[Distribuire il ruolo del server VIS in Skype for Business Server](deploy-the-vis-server-role.md)

[Pianificare video Interop server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Creare e pubblicare una nuova topologia in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
