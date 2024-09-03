--- verifier.c  2024-09-02 20:46:03.000000000 -0700
+++ md-verifier.c       2024-09-02 21:18:11.362964817 -0700
@@ -18727,7 +18727,7 @@ static int fixup_call_args(struct bpf_ve
                         * have to be rejected, since interpreter doesn't support them yet.
                         */
                        verbose(env, "callbacks are not allowed in non-JITed programs\n");
-                       return -EINVAL;
+                       return -ENOTSUPP;
                }
 
                if (!bpf_pseudo_call(insn))
