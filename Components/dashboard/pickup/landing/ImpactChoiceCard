import React from 'react';
import { Button } from '@/components/ui/button';
import { CheckCircle } from 'lucide-react';

export default function ImpactChoiceCard({ title, description, features, buttonText, buttonColor, icon: Icon, onButtonClick }) {
  return (
    <div className="bg-white p-8 rounded-2xl shadow-xl border border-gray-100 flex flex-col">
      <div className="flex items-center gap-3 mb-4">
        <Icon className={`w-8 h-8 ${buttonColor === 'bg-emerald-500' ? 'text-emerald-500' : 'text-orange-500'}`} />
        <h3 className="text-2xl font-bold text-gray-800">{title}</h3>
      </div>
      <p className="text-gray-600 mb-6 text-sm">{description}</p>
      <ul className="space-y-3 mb-8 text-sm">
        {features.map((feature, index) => (
          <li key={index} className="flex items-center gap-2 text-gray-700">
            <CheckCircle className="w-5 h-5 text-emerald-500 flex-shrink-0" />
            <span>{feature}</span>
          </li>
        ))}
      </ul>
      <Button 
        className={`${buttonColor} hover:opacity-90 text-white font-semibold py-3 text-base mt-auto`}
        onClick={onButtonClick}
      >
        {buttonText}
      </Button>
    </div>
  );
}