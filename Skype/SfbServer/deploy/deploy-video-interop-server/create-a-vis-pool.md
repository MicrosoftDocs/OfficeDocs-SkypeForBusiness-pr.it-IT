---
title: Creare un pool VIS in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Riepilogo: creare un pool di video Interop server in Skype for Business Server tramite Generatore di topologie.'
ms.openlocfilehash: dc97fde4447778be20cb60d86cddac65b663c321
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235662"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Creare un pool VIS in Skype for Business Server
 
**Riepilogo:** Creare un pool di video Interop server in Skype for Business Server tramite Generatore di topologie.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Creare un pool VIS o VIS tramite Generatore di topologie

1. Aprire Generatore di topologia nel server front-end. Dal riquadro sinistro di generatore di topologia, fare clic con il pulsante destro del mouse sui **pool di video Interop server** e scegliere **nuovo pool**di interoperabilità video. 
    
2. Verrà aperta una procedura guidata **Crea un nuovo pool di** interoperabilità per il video. Specificare il nome di dominio completo del pool per il nuovo server di interoperabilità video e selezionare **questo pool ha un server** o il **pool ha più server** in base al requisito, quindi premere **Avanti**.
    
    Se si vuole distribuire un pool di interoperabilità video per ottenere una disponibilità elevata, selezionare **questo pool include più server**. Tieni presente che questa opzione: 
    
    - È necessario distribuire il bilanciamento del carico DNS per supportare i pool di server di interoperabilità video. 
    
   - Nella pagina successiva, per l'elemento **Definisci i computer in questo pool** , immettere il **nome di dominio completo del computer** di ogni server nel pool nel campo di testo e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per aggiungere un altro server di interoperabilità video al pool. Dopo aver definito tutti i computer nel pool, premere **Avanti**.
    
     Se si vuole distribuire un solo server di interoperabilità video nel pool perché non è necessaria una disponibilità elevata, selezionare **questo pool ha un server** e premere **Avanti**.
    
3. Selezionare il pool di hop successivo/FE nell'elenco a discesa e premere **Avanti**.
    
4. Selezionare un pool di bordi da associare al VIS e premere **fine**.
    
5. Impostare una porta TCP o TLS.
    
    Selezionare il server di interoperabilità video appena aggiunto dal riquadro sinistro di generatore di topologia, fare clic con il pulsante destro del mouse e scegliere **modifica proprietà**. Abilitare o aggiornare la porta TCP o TLS per ogni requisito e scegliere **OK**. Anche se per impostazione predefinita viene aggiunto TLS, solo TCP è stato completamente testato con Cisco Unified Communications Manager (CallManager o CUCM).
    
6. Aggiungere un gateway video. A questo scopo, Espandi i componenti condivisi, fai clic con il pulsante destro del mouse su **gateway video** e seleziona **nuovo gateway video**.
    
7. Specificare il nome completo o l'indirizzo IP del gateway video. Il gateway video può essere in un sottodominio o in un dominio diverso. Il CUCM usato dal VTCs del sistema funge da gateway video.
    
8. Selezionare IPv4 o IPv6 in base alle esigenze. È possibile usare tutti gli indirizzi IP configurati o limitare l'utilizzo del servizio agli indirizzi IP selezionati.
    
9. Selezionare la porta di ascolto del gateway video. Selezionare il protocollo di trasporto (TCP o TLS) e associarlo a un server di interoperabilità video configurato per un trunk SIP video. Il protocollo di trasporto per il gateway video deve corrispondere al protocollo di trasporto configurato per il VIS.
    
10. Dopo il completamento del passaggio precedente, viene aggiunto un trunk video SIP corrispondente. Fai clic con il pulsante destro del mouse sul trunk video SIP e seleziona il trunk appena aggiunto. Il nome del trunk SIP video, il server di interoperabilità video associato, il protocollo di trasporto SIP e la porta possono essere modificati. 
    
    > [!NOTE]
    >  Un server di interoperabilità video supporta i trunk 1: N. È quindi possibile aggiungere più trunk, associati a un singolo server di interoperabilità video, in cui ogni trunk termina in un gateway video diverso. La limitazione è che un gateway video specifico include uno e un solo trunk che possono essere definiti nella distribuzione di Skype for Business Server.
  
11. Pubblicare il documento della topologia come descritto in [creare e pubblicare una nuova topologia in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Per migliorare la resilienza, è consigliabile configurare un secondo server di interoperabilità video o un pool VIS oppure un pool Front-End di backup. Per altre informazioni, Vedi [meccanismi](../../plan-your-deployment/video-interop-server.md#resiliency) di resilienza.
  
Ora tutte le attività eseguite con generatore di topologie devono essere completate. Procedere con l'installazione del software nel nuovo server o server VIS.
## <a name="see-also"></a>Vedere anche

[Distribuire il ruolo del server VIS in Skype for Business Server](deploy-the-vis-server-role.md)

[Pianificare il video Interop server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Creare e pubblicare una nuova topologia in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)
