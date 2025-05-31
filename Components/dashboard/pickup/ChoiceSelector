import React from 'react';
import { motion } from 'framer-motion';
import { Card } from "@/components/ui/card";
import { DollarSign, Heart, Gift, TrendingUp } from "lucide-react";

export default function ChoiceSelector({ selectedChoice, onChoiceChange, estimatedValue, pointsEquivalent }) {
  const choices = [
    {
      id: 'earn',
      title: 'Earn Money',
      description: 'Get cash for your recyclables',
      icon: DollarSign,
      value: `₹${(estimatedValue * 0.75).toFixed(2)}`, // 75% after handling fee
      subtitle: '(After 25% handling fee)',
      gradient: 'from-green-400 to-green-600',
      bgColor: 'bg-green-50',
      borderColor: 'border-green-300'
    },
    {
      id: 'donate',
      title: 'Donate for Points',
      description: 'Convert to points for rewards',
      icon: Heart,
      value: `${Math.floor(estimatedValue * 10)} points`,
      subtitle: 'Redeem for vouchers & rewards',
      gradient: 'from-purple-400 to-purple-600',
      bgColor: 'bg-purple-50',
      borderColor: 'border-purple-300'
    }
  ];

  return (
    <div className="space-y-6">
      <div>
        <h3 className="text-lg font-semibold text-gray-900 mb-2">How would you like to proceed?</h3>
        <p className="text-gray-600 text-sm">Choose whether to earn money or donate for points</p>
      </div>

      <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
        {choices.map((choice) => (
          <motion.div
            key={choice.id}
            whileHover={{ scale: 1.02 }}
            whileTap={{ scale: 0.98 }}
          >
            <Card 
              className={`p-6 cursor-pointer transition-all duration-300 border-2 ${
                selectedChoice === choice.id 
                  ? `${choice.borderColor} ${choice.bgColor} shadow-lg` 
                  : 'border-gray-200 hover:border-gray-300 hover:shadow-md'
              }`}
              onClick={() => onChoiceChange(choice.id)}
            >
              <div className="text-center">
                <div className={`w-16 h-16 mx-auto mb-4 rounded-2xl bg-gradient-to-br ${choice.gradient} flex items-center justify-center`}>
                  <choice.icon className="w-8 h-8 text-white" />
                </div>
                
                <h4 className="text-xl font-bold text-gray-900 mb-2">{choice.title}</h4>
                <p className="text-gray-600 text-sm mb-4">{choice.description}</p>
                
                <div className="text-2xl font-bold text-gray-900 mb-1">{choice.value}</div>
                <p className="text-xs text-gray-500">{choice.subtitle}</p>
                
                {choice.id === 'donate' && (
                  <div className="mt-4 p-3 bg-white rounded-xl border border-purple-200">
                    <div className="flex items-center justify-center gap-2 text-sm text-purple-600">
                      <Gift className="w-4 h-4" />
                      <span>Unlock exclusive rewards</span>
                    </div>
                  </div>
                )}
                
                {choice.id === 'earn' && (
                  <div className="mt-4 p-3 bg-white rounded-xl border border-green-200">
                    <div className="flex items-center justify-center gap-2 text-sm text-green-600">
                      <TrendingUp className="w-4 h-4" />
                      <span>Direct bank transfer</span>
                    </div>
                  </div>
                )}
              </div>
              
              {selectedChoice === choice.id && (
                <motion.div
                  initial={{ scale: 0 }}
                  animate={{ scale: 1 }}
                  className="absolute top-4 right-4 w-6 h-6 bg-emerald-500 rounded-full flex items-center justify-center"
                >
                  <span className="text-white text-sm">✓</span>
                </motion.div>
              )}
            </Card>
          </motion.div>
        ))}
      </div>

      {selectedChoice && (
        <motion.div
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          className="p-4 bg-gradient-to-r from-emerald-50 to-blue-50 rounded-2xl border border-emerald-200"
        >
          <div className="flex items-center gap-3">
            <div className="text-2xl">🐕</div>
            <div>
              <p className="font-medium text-gray-900">
                {selectedChoice === 'donate' 
                  ? "Woof! Your donation will help make the planet cleaner! 🌍" 
                  : "Great choice! Every bit of recycling helps our environment! 💚"
                }
              </p>
            </div>
          </div>
        </motion.div>
      )}
    </div>
  );
}