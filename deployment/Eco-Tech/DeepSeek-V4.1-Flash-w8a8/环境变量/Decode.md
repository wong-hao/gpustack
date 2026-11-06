自定义镜像：
quay.io/ascend/vllm-ascend:v0.30.0-openeuler-with-router

后端参数：
--data-parallel-size=8
--tensor-parallel-size=2
--max-model-len 1048576
--enable-expert-parallel
--seed 1024
--max-num-batched-tokens 400
--max-num-seqs 32
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
--additional-config '{"ascend_compilation_config":{"enable_npugraph_ex":true,"enable_static_kernel":false},"enable_cpu_binding":true,"multistream_overlap_shared_expert":true,"recompute_scheduler_enable":true}'
--compilation-config '{"cudagraph_mode":"FULL_DECODE_ONLY"}'
--no-enable-prefix-caching
--gpu-memory-utilization 0.9
--speculative-config '{"num_speculative_tokens":5,"method":"dspark"}'

环境变量：
VLLM_ENGINE_READY_TIMEOUT_S 360000
VLLM_USE_V2_MODEL_RUNNER 0
HCCL_INTRA_ROCE_ENABLE 1
HCCL_CONNECT_TIMEOUT 1200
HCCL_BUFFSIZE 1800
VLLM_EXECUTE_MODEL_TIMEOUT_SECONDS 30000
HCCL_EXEC_TIMEOUT 204
GPUSTACK_MODEL_RUNTIME_SHM_SIZE_GIB 500