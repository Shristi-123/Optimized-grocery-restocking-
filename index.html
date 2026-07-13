import { kv } from '@vercel/kv';

// Generic key-value API used by the Stock Ledger frontend.
// GET  /api/kv?key=products        -> { key, value }
// POST /api/kv?key=products  body: { value }  -> { key, value }
export default async function handler(req, res) {
  const { key } = req.query;
  if (!key || typeof key !== 'string') {
    return res.status(400).json({ error: 'A "key" query parameter is required.' });
  }

  if (req.method === 'GET') {
    try {
      const value = await kv.get(key);
      return res.status(200).json({ key, value: value ?? null });
    } catch (e) {
      console.error('KV read failed', e);
      return res.status(500).json({ error: 'Failed to read from storage.' });
    }
  }

  if (req.method === 'POST') {
    try {
      const { value } = req.body || {};
      if (typeof value !== 'string') {
        return res.status(400).json({ error: 'Request body must include a string "value".' });
      }
      await kv.set(key, value);
      return res.status(200).json({ key, value });
    } catch (e) {
      console.error('KV write failed', e);
      return res.status(500).json({ error: 'Failed to write to storage.' });
    }
  }

  res.setHeader('Allow', ['GET', 'POST']);
  return res.status(405).json({ error: `Method ${req.method} not allowed.` });
}
