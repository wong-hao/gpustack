FROM quay.io/ascend/vllm-ascend:v0.30.0-openeuler

# 安装 vllm-router（PyPI 提供 aarch64 预编译包）
RUN pip install --no-cache-dir vllm-router && \
    pip cache purge

# 可选：验证安装
RUN python3 -c "import vllm_router; print('vllm-router installed')" || \
    vllm-router --help > /dev/null && echo "router CLI available"

CMD ["/bin/bash"]