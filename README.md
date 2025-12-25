import { useQuery, useMutation, useQueryClient } from "@tanstack/react-query";
import { api, buildUrl, type InsertPaymentLink } from "@shared/routes";

// ============================================
// Payment Links Hooks
// ============================================

// GET /api/links
export function usePaymentLinks() {
  return useQuery({
    queryKey: [api.paymentLinks.list.path],
    queryFn: async () => {
      const res = await fetch(api.paymentLinks.list.path);
      if (!res.ok) throw new Error("Failed to fetch payment links");
      return api.paymentLinks.list.responses[200].parse(await res.json());
    },
  });
}

// GET /api/links/:id
export function usePaymentLink(id: number) {
  return useQuery({
    queryKey: [api.paymentLinks.get.path, id],
