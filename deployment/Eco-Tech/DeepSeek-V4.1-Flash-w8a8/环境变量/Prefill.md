自定义镜像：
quay.io/ascend/vllm-ascend:v0.30.0-openeuler-with-router

后端参数：
--data-parallel-size=4
--tensor-parallel-size=4
--max-model-len 1048576
--enable-expert-parallel
--seed 1024
--max-num-batched-tokens 8192
--max-num-seqs 16
--async-scheduling
--block-size 128
--trust-remote-code
--tokenizer-mode deepseek_v41
--reasoning-parser deepseek_v41
--tool-call-parser deepseek_v41
--enable-auto-tool-choice
--safetensors-load-strategy lazy
--quantization ascend
--engram-config '{"cpu_offload":true,"dp_shared_memory":true}'
--enforce-eager
--additional-config '{"enable_cpu_binding":true,"enable_dsa_cp":true,"enable_flashcomm1":true,"enable_shared_expert_dp":true}'
--enable-prefix-caching
--gpu-memory-utilization 0.9
--speculative-config '{"num_speculative_tokens":5,"method":"dspark"}'

环境变量：
VLLM_ENGINE_READY_TIMEOUT_S 360000
VLLM_USE_V2_MODEL_RUNNER 0
HCCL_INTRA_ROCE_ENABLE 1
HCCL_CONNECT_TIMEOUT 1200
HCCL_BUFFSIZE 1024
TASK_QUEUE_ENABLE 1
VLLM_RPC_TIMEOUT 3600000
VLLM_EXECUTE_MODEL_TIMEOUT_SECONDS 30000
HCCL_EXEC_TIMEOUT 204
GPUSTACK_MODEL_RUNTIME_SHM_SIZE_GIB 500