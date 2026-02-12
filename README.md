```mermaid
graph LR
    subgraph Ingestion
    A[Supply Chain Data] --> SC[Procurement Logic]
    B[Energy Audit Data] --> EN[Energy Logic]
    end

    subgraph Intelligence_Kernel
    SC -->|Flag High-Cost Asset| MEM[(System Memory JSON)]
    EN -->|Cross-Reference| MEM
    MEM -->|Contextual Analysis| LLM{Llama 3.2 Local}
    end

    subgraph Reporting_Layer
    LLM -->|Generate Decision| LOG[Neural_Log.txt]
    LOG -->|Live Feed| DASH[Streamlit Dashboard]
    DASH -->|Export| PDF[Official Audit PDF]
    end
